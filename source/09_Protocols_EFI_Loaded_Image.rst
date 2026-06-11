
.. _protocols-efi-loaded-image:

Protocols - EFI Loaded Image
=============================

This section defines EFI_LOADED_IMAGE_PROTOCOL and the EFI_LOADED_IMAGE_DEVICE_PATH_PROTOCOL. Respectively, these protocols describe an Image that has been loaded into memory and specifies the device path used when a PE/COFF image was loaded through the EFI Boot Service LoadImage(). These descriptions include the source from which the image was loaded, the current location of the image in memory, the type of memory allocated for the image, and the parameters passed to the image when it was invoked.


.. _efi-loaded-image-protocol:

EFI Loaded Image Protocol
-------------------------

EFI_LOADED_IMAGE_PROTOCOL
#########################


**Summary**

Can be used on any image handle to obtain information about the loaded image.

**GUID**

.. code-block::

   #define EFI_LOADED_IMAGE_PROTOCOL_GUID \
     {0x5B1B31A1,0x9562,0x11d2,\
       {0x8E,0x3F,0x00,0xA0,0xC9,0x69,0x72,0x3B}}

**Revision Number**

.. code-block::

   #define EFI_LOADED_IMAGE_PROTOCOL_REVISION 0x1000

**Protocol Interface Structure**

.. code-block:: 

   typedef struct {
      UINT32                        Revision;
      EFI_HANDLE                    ParentHandle;
      EFI_System_Table              *SystemTable;

      // Source location of the image
      EFI_HANDLE                    DeviceHandle;
      EFI_DEVICE_PATH_PROTOCOL      *FilePath;
      VOID                          *Reserved;

      // Image’s load options
      UINT32                        LoadOptionsSize;
      VOID                          *LoadOptions;

      // Location where image was loaded
      VOID                          *ImageBase;
      UINT64                        ImageSize;
      EFI_MEMORY_TYPE               ImageCodeType;
      EFI_MEMORY_TYPE               ImageDataType;
      EFI_IMAGE_UNLOAD              Unload;
   } EFI_LOADED_IMAGE_PROTOCOL;

**Parameters**

Revision
  Defines the revision of the EFI_LOADED_IMAGE_PROTOCOL structure. All future revisions will be backward compatible to the current revision. 

ParentHandle 
  Parent image’s image handle. NULL if the image is loaded directly from the firmware’s boot manager. Type EFI_HANDLE is defined in Services – Boot Services.

SystemTable 
  The image’s EFI system table pointer. Type EFI_SYSTEM_TABLE defined in :ref:`efi-system-table`.

DeviceHandle 
  The device handle that the EFI Image was loaded from. Type EFI_HANDLE is defined in Services – Boot Services. 

FilePath 
  A pointer to the file path portion specific to DeviceHandle that the EFI Image was loaded from. EFI_DEVICE_PATH_PROTOCOL  is defined in  :ref:`efi-device-path-protocol` .

Reserved 
  Reserved. DO NOT USE.

LoadOptionsSize 
  The size in bytes of LoadOptions.

LoadOptions 
  A pointer to the image’s binary load options. See the OptionalData parameter in the :ref:`load-options` section of the Boot Manager chapter for information on the source of the LoadOptions data.

ImageBase 
  The base address at which the image was loaded.

ImageSize 
  The size in bytes of the loaded image.

ImageCodeType 
  The memory type that the code sections were loaded as. Type EFI_MEMORY_TYPE is defined in Services – Boot Services.

ImageDataType 
  The memory type that the data sections were loaded as. Type *EFI_MEMORY_TYPE* is defined in in Services – Boot Services. 

Unload 
  Function that unloads the image - see :numref:`efi-loaded-image-protocol-unload`.

**Description**

Each loaded image has an image handle that supports EFI_LOADED_IMAGE_PROTOCOL. When an image is started, it is passed the image handle for itself. The image can use the handle to obtain its relevant image data stored in the EFI_LOADED_IMAGE_PROTOCOL structure, such as its load options.


.. _efi-loaded-image-protocol-unload:

EFI_LOADED_IMAGE_PROTOCOL.Unload()
##################################

**Summary**

Unloads an image from memory.

**Prototype**

.. code-block::
  
   typedef  
   EFI_STATUS
   (EFIAPI *EFI_IMAGE_UNLOAD) (
     IN EFI_HANDLE               ImageHandle,
     );

**Parameters**

ImageHandle 
  The handle to the image to unload. Type EFI_HANDLE  :ref:`driver-model-boot-services`

**Description**

The Unload() function is a callback that a driver registers to do cleanup when the UnloadImage boot service function is called.

**Status Codes Returned**

.. list-table::
   :widths: 35 70
   :class: longtable

   * - EFI_SUCCESS
     - The image was unloaded.
   * - EFI_INVALID_PARAMETER 
     - The *ImageHandle* was not valid.


.. _efi-loaded-image-device-path-protocol:

EFI Loaded Image Device Path Protocol
-------------------------------------


EFI_LOADED_IMAGE_DEVICE_PATH_PROTOCOL
#####################################

**Summary**

When installed, the Loaded Image Device Path Protocol specifies the device path that was used when a PE/COFF image was loaded through the EFI Boot Service LoadImage().

**GUID**

.. code-block::

   #define EFI_LOADED_IMAGE_DEVICE_PATH_PROTOCOL_GUID \
      {0xbc62157e,0x3e33,0x4fec,\
     {0x99,0x20,0x2d,0x3b,0x36,0xd7,0x50,0xdf}}

**Description**

The Loaded Image Device Path Protocol uses the same protocol interface structure as the Device Path Protocol defined in Chapter 9. The only difference between the Device Path Protocol and the Loaded Image Device Path Protocol is the protocol GUID value. 

The Loaded Image Device Path Protocol must be installed onto the image handle of a PE/COFF image loaded through the EFI Boot Service LoadImage(). A copy of the device path specified by the *DevicePath* parameter to the EFI Boot Service LoadImage() is made before it is installed onto the image handle. It is legal to call LoadImage() for a buffer in memory with a NULL *DevicePath* parameter. In this case, the Loaded Image Device Path Protocol is installed with a NULL interface pointer.

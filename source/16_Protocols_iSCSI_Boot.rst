.. _protocols-iscsi-boot:

Protocols — iSCSI Boot 
=======================

.. _protocols-iscsi-boot-overview:

Overview
--------

The iSCSI protocol defines a transport for SCSI data over TCP/IP. It also provides an interoperable solution that takes advantage of existing internet infrastructure, management facilities, and addresses distance limitations. The iSCSI protocol specification was developed by the Internet Engineering Task Force (IETF) and is SCSI Architecture Model-2 (SAM-2) compliant. iSCSI encapsulates block-oriented SCSI commands into iSCSI Protocol Data Units (PDU) that traverse the network over TCP/IP. iSCSI defines a Session, the initiator and target nexus (I-T nexus), which could be a bundle of one or more TCP connections. 

Similar to other existing mass storage protocols like Fibre Channel and parallel SCSI, boot over iSCSI is an important functionality. This document will attempt to capture the various cases for iSCSI boot and common up with generic EFI protocol changes to address them.


.. _iscsi-uefi-driver-layering:

iSCSI UEFI Driver Layering
##########################

iSCSI UEFI Drivers may exist in two different forms:

- **iSCSI UEFI Driver on a NIC**:
       The driver will be layered on top of the networking layers. It will use the DHCP, IP, and TCP and packet level interface protocols of the UEFI networking stack. The driver will use an iSCSI software initiator. 

- **iSCSI UEFI Driver on a Host Bus Adapter (HBA)that may use an offloading engine such as TOE (or anyother TCP offload card):** 
      The driver will be layered on top of the TOE TCP interfaces. It will use the DHCP, IP, TCP protocols of the TOE. The driver will present itself as a SCSI device driver using interfaces such as *EFI_EXT_SCSI_PASS_THRU_PROTOCOL* . 

To help in detecting iSCSI UEFI Drivers and their capabilities, the iSCSI UEFI driver handle must include an instance of the *EFI_ADAPTER_INFORMATION_PROTOCOL* with a *EFI_ADAPTER_INFO_NETWORK_BOOT* structure.


.. _efi-iscsi-initiator-name-protocol: 

EFI iSCSI Initiator Name Protocol
---------------------------------

This protocol sets and obtains the iSCSI Initiator Name. The iSCSI Initiator Name protocol builds a default iSCSI name. The iSCSI name configures using the programming interfaces defined below. Successive configuration of the iSCSI initiator name overwrites the previously existing name. Once overwritten, the previous name will not be retrievable. Setting an iSCSI name string that is zero length is illegal. The maximum size of the iSCSI Initiator Name is 224 bytes (including the **NULL** terminator).


.. _efi_iscsi_initiator_name_protocol:

EFI_ISCSI_INITIATOR_NAME_PROTOCOL
#################################


**Summary**

iSCSI Initiator Name Protocol for setting and obtaining the iSCSI Initiator Name.


**GUID**

.. code-block::

   #define EFI_ISCSI_INITIATOR_NAME_PROTOCOL_GUID \
     {0x59324945, 0xec44, 0x4c0d, \
       {0xb1, 0xcd, 0x9d, 0xb1, 0x39, 0xdf, 0x07, 0x0c}}


**Protocol Interface Structure**

.. code-block::

   typedef struct _EFI_ISCSI_INITIATOR_NAME_PROTOCOL {
     EFI_ISCSI_INITIATOR_NAME_GET                    Get;
     EFI_ISCSI_INITIATOR_NAME_SET                    Set;
   }   EFI_ISCSI_INITIATOR_NAME_PROTOCOL; 


**Parameters**

Get
  Used to retrieve the iSCSI Initiator Name.

Set
  Used to set the iSCSI Initiator Name. 


**Description**

The *EFI_ISCSI_INIT_NAME_PROTOCOL* provides the ability to get and set the iSCSI Initiator Name.


.. _efi-iscsi-initiator-name-protocol-get:

EFI_ISCSI_INITIATOR_NAME_PROTOCOL. Get()
########################################


**Summary**

Retrieves the current set value of iSCSI Initiator Name.


**Prototype**

.. code-block:: 
  
   typedef EFI_STATUS
   (EFIAPI *EFI_ISCSI_INITIATOR_NAME_GET) (
     IN EFI_ISCSI_INITIATOR_NAME_PROTOCOL    *This,
     IN OUT UINTN                            *BufferSize,
     OUT VOID                                *Buffer
     );


**Parameters**

This
  Pointer to the *EFI_ISCSI_INITIATOR_NAME_PROTOCOL* instance.

BufferSize
  Size of the buffer in bytes pointed to by Buffer / Actual size of the variable data buffer.

Buffer
  Pointer to the buffer for data to be read. The data is a null-terminated UTF-8 encoded string. The maximum length is 223 characters, including the null-terminator.


**Description**

This function will retrieve the iSCSI Initiator Name from Non-volatile memory.


**Status Codes Returned**

.. list-table::
   :widths: 35 70
   :class: longtable

   * - EFI_SUCCESS
     - Data was successfully retrieved into the provided buffer and the *BufferSize* was sufficient to handle the iSCSI initiator name
   * - EFI_BUFFER_TOO_SMALL
     - *BufferSize* is too small for the result. *BufferSize* will be updated with the size required to complete the request. *Buffer* will not be affected.
   * - EFI_INVALID_PARAMETER
     - *BufferSize* is **NULL**. *BufferSize* and *Buffer* will not be affected.
   * - EFI_INVALID_PARAMETER
     - *Buffer* is **NULL**. *BufferSize* and *Buffer* will not be affected.
   * - EFI_DEVICE_ERROR
     - The iSCSI initiator name could not be retrieved due to a hardware error.


.. _efi-iscsi-initiator-name-protocol-set:


EFI_ISCSI_INITIATOR_NAME_PROTOCOL.Set()
#######################################


**Summary**

Sets the iSCSI Initiator Name.


**Prototype**

.. code-block:: 
  
   typedef EFI_STATUS
   (EFIAPI *EFI_ISCSI_INITIATOR_NAME_SET) (
     IN EFI_ISCSI_INITIATOR_NAME_PROTOCOL       *This,
     IN OUT UINTN                               *BufferSize,
     IN VOID                                    *Buffer
     );


**Parameters**

This   
  Pointer to the *EFI_ISCSI_INITIATOR_NAME_PROTOCOL* instance

BufferSize
  Size of the buffer in bytes pointed to by Buffer.

Buffer
  Pointer to the buffer for data to be written. The data is a null-terminated UTF-8 encoded string. The maximum length is 223 characters, including the null-terminator.


**Description**

This function will set the iSCSI Initiator Name into Non-volatile memory.


**Status Codes Returned**

.. list-table::
   :widths: 35 70
   :class: longtable

   * - EFI_SUCCESS
     - Data was successfully stored by the protocol
   * - EFI_UNSUPPORTED
     - Platform policies do not allow for data to be written
   * - EFI_INVALID_PARAMETER
     - *BufferSize* exceeds the maximum allowed limit. *BufferSize* will be updated with the maximum size required to complete the request.
   * - EFI_INVALID_PARAMETER
     - *Buffersize* is **NULL**. *BufferSize* and *Buffer* will not be affected
   * - EFI_INVALID_PARAMETER
     - *Buffer* is **NULL**. *BufferSize* and *Buffer* will not be affected.
   * - EFI_DEVICE_ERROR
     - The data could not be stored due to a hardware error.
   * - EFI_OUT_OF_RESOURCES
     - Not enough storage is available to hold the data
   * - EFI_PROTOCOL_ERROR
     - Input iSCSI initiator name does not adhere to RFC 3720 (and other related protocols)
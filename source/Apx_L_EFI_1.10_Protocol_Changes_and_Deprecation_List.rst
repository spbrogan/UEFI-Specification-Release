
.. _appendix-l-efi-1-10-protocol-changes-and-deprecation-list-APX-L-efi-1-10-protocol-changes-and-deprecation-list:

EFI 1.10 Protocol Changes and Deprecation List
================================================


.. _protocol-and-guid-name-changes-from-efi-1.10_efi_1.10_protocol_changes_and_deprecation_list:

Protocol and GUID Name Changes from EFI 1.10
--------------------------------------------

This appendix lists the Protocol , GUID, and revision identifier name changes and the deprecated protocols compared to the EFI Specification 1.10. The protocols listed are not Runtime, Reentrant or MP Safe. Protocols are listed by EFI 1.10 name. 

For protocols in the table whose TPL is not <= TPL_NOTIFY: 

This function must be called at a TPL level less then or equal to %%%%. 

%%%% is TPL_CALLBACK or TPL_APPLICATION. The <= is done via text.

.. _protocol-name-changes_efi_1.10_protocol_changes_and_deprecation_list:



.. list-table:: Protocol Name changes
   :name: protocol-name-changes
   :widths: 50,50


   * - **EFI 1.10 Protocol Name**
     - **UEFI Specification Protocol Name**
   * - EFI_LOADED_IMAGE
     - EFI_LOADED_IMAGE_PROTOCOL
   * - TPL
     - <= TPL_NOTIFY
   * - New GUID name
     - EFI_LOADED_IMAGE_PROTOCOL_GUID
   * - EFI_DEVICE_PATH
     - EFI_DEVICE_PATH_PROTOCOL
   * - TPL
     - <= TPL_NOTIFY
   * - New GUID name
     - EFI_DEVICE_PATH_PROTOCOL_GUID
   * - SIMPLE_INPUT_INTERFACE
     - EFI_SIMPLE_INPUT_PROTOCOL
   * - TPL
     - <= TPL_APPLICATION
   * - New GUID name
     - EFI_SIMPLE_INPUT_PROTOCOL_GUID
   * - SIMPLE_TEXT_OUTPUT_INTERFACE
     - EFI_SIMPLE_TEXT_OUTPUT_PROTOCOL
   * - TPL
     - <=TPL_CALLBACK
   * - New GUID name
     - EFI_SIMPLE_TEXT_OUTPUT_PROTOCOL_GUID
   * - SERIAL_IO_INTERFACE
     - EFI_SERIAL_IO_PROTOCOL
   * - TPL
     - <=TPL_CALLBACK
   * - New GUID name
     - EFI_SERIAL_IO_PROTOCOL_GUID
   * - EFI_LOAD_FILE_INTERFACE
     - EFI_LOAD_FILE_PROTOCOL
   * - TPL
     - <= TPL_NOTIFY
   * - New GUID name
     - EFI_LOAD_FILE_PROTOCOL_GUID
   * - EFI_FILE_IO_INTERFACE
     - EFI_SIMPLE_FILE_SYSTEM_PROTOCOL
   * - TPL
     - <=TPL_CALLBACK
   * - New GUID name
     - EFI_FILE_SYSTEM_PROTOCOL_GUID
   * - EFI_FILE
     - EFI_FILE_PROTOCOL
   * - TPL
     - <= TPL_CALLBACK
   * - New GUID name
     - EFI_FILE_PROTOCOL_GUID
   * - EFI_DISK_IO
     - EFI_DISK_IO_PROTOCOL
   * - TPL
     - <=TPL_CALLBACK
   * - New GUID name
     - EFI_DISK_IO_PROTOCOL_GUID
   * - EFI_BLOCK_IO
     - EFI_BLOCK_IO_PROTOCOL
   * - TPL
     - <=TPL_CALLBACK
   * - New GUID name
     - EFI_BLOCK_IO_PROTOCOL_GUID
   * - UNICODE_COLLATION_INTERFACE
     - EFI_UNICODE_COLLATION_PROTOCOL
   * - TPL
     - <= TPL_NOTIFY
   * - New GUID name
     - EFI_UNICODE_COLLATION_PROTOCOL_GUID
   * - EFI_SIMPLE_NETWORK
     - EFI_SIMPLE_NETWORK_PROTOCOL
   * - TPL
     - <=TPL_CALLBACK
   * - New GUID name
     - EFI_SIMPLE_NETWORK_PROTOCOL_GUID
   * - EFI_NETWORK_INTERFACE_IDENTIFIER  \_INTERFACE
     - EFI_NETW ORK_INTERFACE_IDENTIFIER _PROTOCOL
   * - TPL
     - <= TPL_NOTIFY
   * - New GUID name
     - EFI_NETWORK_INTERFACE_IDENTIFIER _PROTOCOL_GUID
   * - EFI_PXE_BASE_CODE
     - EFI_PXE_BASE_CODE_PROTOCOL
   * - TPL
     - <= TPL_NOTIFY
   * - New GUID name
     - EFI_PXE_BASE_CODE \_PROTOCOL_GUID
   * - EFI_PXE_BASE_CODE_CALLBACK
     - EFI_PXE_BASE_CODE_CALLBACK_PROTOCOL
   * - TPL
     - <= TPL_NOTIFY
   * - New GUID name
     - EFI_PXE _BASE_CODE_CALLBACK_PROTOCOL
       _GUID
   * - EFI_DEVICE_IO_INTERFACE
     - EFI_DEVICE_IO_PROTOCOL
   * - TPL
     - <= TPL_NOTIFY
   * - New GUID name
     - EFI_DEVICE_IO_PROTOCOL_GUID





.. _revision-identifier-name-changes_efi_1.10_protocol_changes_and_deprecation_list:



.. list-table:: Revision Identifier Name Changes
   :name: revision-identifier-name-changes
   :widths: 40,60

   * - **EFI 1.10 Revision Identifier Name**
     - **UEFI Specification Revision Identifier Name**
   * - EFI_LOADED_IMAGE_INFORMATION
       _REVISION
     - EFI_LOADED_IMAGE_PROTOCOL_REVISION
   * - SERIAL_IO_INTERFACE_REVISION
     - EFI_SERIAL_IO_PROTOCOL_REVISION
   * - EFI_FILE_IO_INTERFACE_REVISION
     - EFI_SIM PLE_FILE_SYSTEM_PROTOCOL
       _REVISION
   * - EFI_FILE_REVISION
     - EFI_FILE_PROTOCOL_REVISION
   * - EFI_DISK_IO_INTERFACE_REVISION
     - EFI_DISK_IO_PROTOCOL_REVISION
   * - EFI_BLOCK_IO_INTERFACE_REVISION
     - EFI_BLOCK_IO_PROTOCOL_REVISION
   * - EFI_SIMPLE_NETWORK_INTERFACE
       _REVISION
     - EFI_SIMPLE_NETWORK_PROTOCOL
       _REVISION
   * - EFI_NETWORK_INTERFACE_IDENTIFIER
       _INTERFACE_REVISION
     - EFI_NETWORK_INTERFACE_IDENTIFIER
       _PROTOCOL_REVISION
   * - EFI_PXE_BASE_CODE
       _INTERFACE_REVISION
     - EFI_PXE_BASE_CODE_PROTOCOL_REVISION
   * - EFI_PXE_BASE_CODE_CALLBACK
       _INTERFACE_REVISION
     - EFI_PXE_BASE_CODE_CALLBACK
       _PROTOCOL_REVISION


.. _deprecated-protocols_efi_1.10_protocol_changes_and_deprecation_list:

Deprecated Protocols
--------------------

**Device I/O Protocol** - The support of the Device I/O Protocol (see EFI 1.1 Chapter 18) has been replaced by the use of the PCI Root Bridge I/O protocols which are described in  :ref:`pci-root-bridge-io-protocol` of the UEFI Specification. Note: certain "legacy" EFI applications such as some of the ones that reside in the EFI Toolkit assume the presence of Device I/O.

**UGA I/O + UGA Draw Protocol** - The support of the UGA \* Protocols (see EFI 1.1 Section 10.7) have been replaced by the use of the EFI Graphics Output Protocol described in :ref:`protocols-console-support` of the UEFI Specification. 

**USB Host Controller Protocol** (version that existed for EFI 1.1) - The support of the USB Host Controller Protocol (see EFI 1.1 Section 14.1) has been replaced by the use of a UEFI instance that covers both USB 1.1 and USB 2.0 support, and is described in :ref:`protocols-usb-support`  of the UEFI Specification. It replaces the pre-existing protocol definition.

**SCSI Passthru Protocol** - The support of the SCSI Passthru Protocol (see EFI 1.1 Section 13.1) has been replaced by the use of the Extended SCSI Passthru Protocol, which is described in :numref:`extended-scsi-pass-thru-protocol`. 

**BIS Protocol** - Remains as an optional protocol.

**Driver Configuration Protocol** - the *EFI_DRIVER_CONFIGURATION_PROTOCOL* has been removed.

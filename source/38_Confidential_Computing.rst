.. _confidential-computing:

Confidential Computing
=======================

In confidential computing, a virtual firmware may support measurement and event log based upon the hardware Trusted Execution Environment (TEE) capability. We need way to provide the abstraction for the hardware TEEs, such as Intel Trust Domain Extension (TDX). This document describes the interface between virtual firmware and virtual guest OS.
The interfaces defined in this document are optional. If the virtual firmware does not support hardware TEE based confidential computing, then the interfaces are not required. If the virtual firmware implements a virtual TPM, then the TCG defined event log, EFI_TCG2_PROTOCOL should be used, while the interfaces defined in this document should not be published.


.. _virtual-platform-cc-event-log:

Virtual Platform CC Event Log
-----------------------------

If a virtual firmware with confidential computing (CC) capability supports measurement and an event is created, virtual firmware should report the event log with the same data structure in TCG Platform Firmware Profile (PFP) specification with EFI_TCG2_EVENT_LOG_FORMAT_TCG_2 format.
The index created by the virtual firmware in the event log should be the index for the confidential computing (CC) measurement register. It is CC vendor specific. 


.. _efi-cc-measurement-protocol:

EFI_CC_MEASUREMENT_PROTOCOL
---------------------------

If a virtual firmware with confidential computing (CC) capability supports measurement, the virtual firmware should produce EFI_CC_MEASUREMENT_PROTOCOL with new GUID EFI_CC_MEASUREMENT_PROTOCOL_GUID to report event log and provide hash capability.


.. _efi_cc_measurement_protocol:

EFI_CC_MEASUREMENT_PROTOCOL
############################

**Summary**

This protocol abstracts the confidential computing (CC) measurement operation in UEFI guest environment.

**GUID**

::

  #define EFI_CC_MEASUREMENT_PROTOCOL_GUID \ 
  {0x96751a3d, 0x72f4, 0x41a6, {0xa7, 0x94, 0xed, 0x5d, 0xe, 0x67, 0xae, 0x6b }}
  Protocol Interface Structure
  typedef struct _EFI_CC_MEASUREMENT_PROTOCOL { 
    EFI_CC_GET_CAPABILITY          GetCapability;
    EFI_CC_GET_EVENT_LOG           GetEventLog;
    EFI_CC_HASH_LOG_EXTEND_EVENT   HashLogExtendEvent;
    EFI_CC_MAP_PCR_TO_MR_INDEX     MapPcrToMrIndex;
  } EFI_CC_MEASUREMENT_PROTOCOL;

**Parameters**

*GetCapability*

Provide protocol capability information and state information. See the GetCapability() function description.

*GetEventLog*

Allow a caller to retrieve the address of a given event log and its last entry. See the GetEventLog() function description.

*HashLogExtendEvent*

Provide callers with an opportunity to extend and optionally log events without requiring knowledge of actual CC command. See the HashLogExtendEvent() function description.

*MapPcrToMrIndex*

Provide callers information on TPM PCR to CC measurement register (MR) mapping. See the MapPcrToMrIndex() function description.

**Description**

The EFI_CC_MEASUREMENT_PROTOCOL is used to abstract the CC measurement related action in CC UEFI guest environment.



EFI_CC_MEASUREMENT_PROTOCOL.GetCapability
##########################################

**Summary**

This service provides protocol capability information and state information.

**Prototype**

::

  typedef
  EFI_STATUS
  (EFIAPI *EFI_CC_GET_CAPABILITY)(
    IN EFI_CC_MEASUREMENT_PROTOCOL        *This,
    IN OUT EFI_CC_BOOT_SERVICE_CAPABILITY *ProtocolCapability
    );

**Parameters**

*This*

The protocol interface pointer.

*ProtocolCapability*

The caller allocates memory for an EFI_CC_BOOT_SERVICE_CAPABILITY structure and sets the size field to the size of the structure allocated. The callee fills in the fields with the EFI protocol capability information and the current EFI CC state information up to the number of fields which fit within the size of the structure passed in.

**Description**

This function provides protocol capability information and state information.

**Status Codes Returned**

.. list-table::
   :widths: 35 70
   :class: longtable 

   * - EFI_SUCCESS
     - | Operation completed successfully.
   * - EFI_INVALID_PARAMETER
     - | One or more of the parameters are incorrect.
       | The ProtocolCapability variable will not be populated.
   * - EFI_DEVICE_ERROR
     - | The command was unsuccessful.
       | The ProtocolCapability variable will not be populated.
   * - EFI_BUFFER_TOO_SMALL
     - | The ProtocolCapability variable is too small to hold the full response. It will be partially populated (required Size field will be set).

**Related Definitions**

::

  typedef struct {
    //
    // Allocated size of the structure
    //
    UINT8                            Size;
    //
    // Version of the EFI_CC_BOOT_SERVICE_CAPABILITY structure.
    // For this version of the protocol,
    // the Major version shall be set to 1
    // and the Minor version shall be set to 0.
    //
    EFI_CC_VERSION                   StructureVersion;
    //
    // Version of the EFI CC MEASUREMENT protocol.
    // For this version of the protocol,
    // the Major version shall be set to 1
    // and the Minor version shall be set to 0.
    //
    EFI_CC_VERSION                   ProtocolVersion;
    //
    // Supported hash algorithms
    //
    EFI_CC_EVENT_ALGORITHM_BITMAP    HashAlgorithmBitmap;
    //
    // Bitmap of supported event log formats
    //
    EFI_CC_EVENT_LOG_BITMAP          SupportedEventLogs;
  
    //
    // Indicate CC type
    //
    EFI_CC_TYPE                      CcType;
  } EFI_CC_BOOT_SERVICE_CAPABILITY;
  
  typedef struct {
    UINT8 Major;
    UINT8 Minor;
  } EFI_CC_VERSION;
  
  typedef UINT32     EFI_CC_EVENT_LOG_BITMAP;
  typedef UINT32     EFI_CC_EVENT_ALGORITHM_BITMAP;
  
  #define EFI_CC_BOOT_HASH_ALG_SHA384     0x00000004
  
  typedef struct {
    UINT8 Type;
    UINT8 SubType;
  } EFI_CC_TYPE;
  
  #define EFI_CC_TYPE_NONE 0
  // 1~0xFF: CC vendor specific. Please refer to 38.4


.. _efi_cc_protocol-geteventlog:

EFI_CC_PROTOCOL.GetEventLog
############################

**Summary**

This service allows a caller to retrieve the address of a given event log and its last entry.

**Prototype**

::

  typedef
  EFI_STATUS
  (EFIAPI *EFI_CC_GET_EVENT_LOG)(
    IN EFI_CC_MEASUREMENT_PROTOCOL        *This,
    IN EFI_CC_EVENT_LOG_FORMAT            EventLogFormat,
    OUT EFI_PHYSICAL_ADDRESS              *EventLogLocation,
    OUT EFI_PHYSICAL_ADDRESS              *EventLogLastEntry,
    OUT BOOLEAN                           *EventLogTruncated
    );

**Parameters**

*This*

The protocol interface pointer.

*EventLogFormat*

The type of event log for which the information is requested.

*EventLogLocation*

A pointer to the memory address of the event log.

*EventLogLastEntry*

If the event log contains more than one entry, this is a pointer to the address of the start of the last entry in the event log in memory.

*EventLogTruncated*

If the event log is missing at least one entry because one event would have exceeded the area allocated for the event, this value is set to TRUE. Otherwise, this value will be FALSE and the event log is complete.

**Description**

This function allows a caller to retrieve the address of a given event log and its last entry.

**Status Codes Returned**

.. list-table::
   :widths: 35 70
   :class: longtable 

   * - EFI_SUCCESS
     - Operation completed successfully.
   * - EFI_INVALID_PARAMETER
     - One or more of the parameters are incorrect.

**Related Definitions**

::

  typedef UINT32                          EFI_CC_EVENT_LOG_FORMAT;
  
  #define EFI_CC_EVENT_LOG_FORMAT_TCG_2   0x00000002


.. _efi_cc_measurement_protocol-haslogextendevent:

EFI_CC_MEASUREMENT_PROTOCOL.HashLogExtendEvent
###############################################

**Summary**

This service provides callers with an opportunity to extend and optionally log events without requiring knowledge of actual CC command.

**Prototype**

::

  typedef
  EFI_STATUS
  (EFIAPI *EFI_CC_GET_EVENT_LOG)(
    IN EFI_CC_MEASUREMENT_PROTOCOL        *This,
    IN UINT64                             Flags,
    IN EFI_PHYSICAL_ADDRESS               DataToHash,
    IN UINT64                             DataToHashLen,
    IN EFI_CC_EVENT                       *EfiTdEvent
    );

**Parameters**

*This*

The protocol interface pointer.

*Flags*

Bitmap providing additional information.

*DataToHash*

Physical address of the start of the data buffer to be hashed.

*DataToHashLen*

The length in bytes of the buffer referenced by DataToHash.

*EfiCcEvent*

Pointer to the data buffer containing information about the event.

**Description**

This function provides callers with an opportunity to extend and optionally log events without requiring knowledge of actual CC command. The extend operation will occur even if the function cannot create an event log entry.

**Status Codes Returned**

.. list-table::
   :widths: 35 70
   :class: longtable 

   * - EFI_SUCCESS
     - Operation completed successfully.
   * - EFI_INVALID_PARAMETER
     - One or more of the parameters are incorrect.
   * - EFI_DEVICE_ERROR
     - The command was unsuccessful.
   * - EFI_VOLUME_FULL
     - The extend operation occurred, but the event could not be written to one or more event logs.
   * - EFI_UNSUPPORTED
     - The PE/COFF image type is not supported.

**Related Definitions**

::

  //
  // This bit is shall be set when an event shall be extended
  // but not logged.
  //
  #define EFI_CC_FLAG_EXTEND_ONLY    0x0000000000000001
  
  //
  // This bit shall be set when the intent is to measure
  // a PE/COFF image.
  //
  #define EFI_CC_FLAG_PE_COFF_IMAGE  0x0000000000000010
  
  typedef UINT32 EFI_CC_MR_INDEX; 
  
  #pragma pack(1)
  
  typedef struct {
    //
    // Size of the event header itself.
    //
    UINT32            HeaderSize;
    //
    // Header version. For this version of this specification,
    // the value shall be 1.
    //
    UINT16            HeaderVersion;
    //
    // Index of the MR that shall be extended.
    //
    EFI_CC_MR_INDEX   MrIndex;
    //
    // Type of the event that shall be extended
    // (and optionally logged).
    //
    UINT32            EventType;
  } EFI_CC_EVENT_HEADER;
  
  typedef struct {
    //
    // Total size of the event including the Size component,
    // the header and the Event data.
    //
    UINT32                Size;
    EFI_CC_EVENT_HEADER   Header;
    UINT8                 Event[1];
  } EFI_CC_EVENT;
  
  #pragma pack()


.. _efi_cc_measurement_protocol-mappcrtomrindex:

EFI_CC_MEASUREMENT_PROTOCOL.MapPcrToMrIndex
#############################################

**Summary**

This service provides callers information on TPM PCR to CC measurement register (MR) mapping.

**Prototype**

::

  typedef
  EFI_STATUS
  (EFIAPI *EFI_CC_MAP_PCR_TO_MR_INDEX)(
    IN EFI_CC_MEASUREMENT_PROTOCOL        *This,
    IN TCG_PCRINDEX                       PcrIndex,
    OUT EFI_CC_MR_INDEX                   *MrIndex
    );

**Parameters**

*This*

The protocol interface pointer.

*PcrIndex*

TPM PCR index.

*MrIndex*

CC Measurement Register index.

**Description**

This function provides callers information on TPM PCR to CC measurement register (MR) mapping. This is CC vendor specific. Please refer to 38.4.

**Status Codes Returned**

.. list-table::
   :widths: 35 70
   :class: longtable 

   * - EFI_SUCCESS
     - Operation completed successfully.
   * - EFI_INVALID_PARAMETER
     - One or more of the parameters are incorrect.
   * - EFI_DEVICE_ERROR
     - The command was unsuccessful.
   * - EFI_VOLUME_FULL
     - The extend operation occurred, but the event could not be written to one or more event logs.
   * - EFI_UNSUPPORTED
     - The PE/COFF image type is not supported.


**Related Definitions**

::

  typedef UINT32 TCG_PCRINDEX;


.. _efi-cc-final-events-table:

EFI CC Final Events Table
--------------------------

All events generated after the invocation of GetEventLog SHALL be stored in an instance of an EFI_CONFIGURATION_TABLE named by the VendorGuid
of EFI_CC_FINAL_EVENTS_TABLE_GUID. The associated table contents SHALL be referenced by the VendorTable of EFI_CC_FINAL_EVENTS_TABLE.

::

  #define EFI_CC_FINAL_EVENTS_TABLE_GUID \ 
  {0xdd4a4648, 0x2de7, 0x4665, {0x96, 0x4d, 0x21, 0xd9, 0xef, 0x5f, 0xb4, 0x46}}
  
  typedef struct {
    //
    // The version of this structure. It shall be set to 1.
    //
    UINT64                  Version;
    //
    // Number of events recorded after invocation of GetEventLog API
    //
    UINT64                  NumberOfEvents;
    //
    // List of events of type CC_EVENT.
    //
    //CC_EVENT              Event[1];
  } EFI_CC_FINAL_EVENTS_TABLE;
  

  #pragma pack(1)
  
  //
  // Crypto Agile Log Entry Format.
  // It is similar with TCG_PCR_EVENT2 except MrIndex.
  //
  typedef struct {
    EFI_CC_MR_INDEX     MrIndex;
    UINT32              EventType;
    TPML_DIGEST_VALUES  Digests;
    UINT32              EventSize;
    UINT8               Event[1];
  } CC_EVENT;
  
  #pragma pack()


.. _vendor-specific-information:

Vendor Specific Information
----------------------------

Intel Trust Domain Extension
##############################

The following table shows the TPM PCR index mapping and CC event log measurement register index interpretation for Intel TDX, where MRTD means Trust Domain Measurement Register and RTMR means Runtime Measurement Register.

.. list-table:: **Mapping for Intel TDX**
   :name: mapping-for-intel-tdx
   :widths: 10 20 20
   :class: longtable 

   * - **TPM PCR Index**
     - **CC Event Log Measurement Register Index**
     - **Intel TDX Measurement Register**
   * - 0
     - 0
     - MRTD
   * - 1, 7
     - 1
     - RTMR[0]
   * - 2~6
     - 2
     - RTMR[1]
   * - 8~15
     - 3
     - RTMR[2]

**Related Definitions**

::

  #define EFI_CC_TYPE_INTEL_TDX  2

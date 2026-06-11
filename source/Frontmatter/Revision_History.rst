.. only:: html
   
   Revision History
   ------------------

.. only:: latex
   
   **Revision History**

Many people have contributed to the contents of this specification, including the following:

  * UEFI Specification Working Group (USWG)
  * Tianocore Community Members
  * Others noted in the Revision History below


**Changes in this release**

.. csv-table::
   :delim: |
   :class: longtable
   :widths: 10 60 30

   **Revision** | **Mantis# - Description** | **Affected Content**
   2.10 | 2205 - Enabling SHA-384/SHA-512 signing scheme for Authenticated Variables | :numref:`using-the-efi-variable-authentication-2-descriptor`
   2.10 | 2207 - EFI_SECURITY_VIOLATION can't be returned by EFI_FIRMWARE_MANAGEMENT_PROTOCOL.GetImage() | :numref:`efi-firmware-management-protocol-getimage`
   2.10 | 2217 - Device Authentication Signature Database | :numref:`globally-defined-variables`, :numref:`signature-database`, :numref:`device-authentication`, :numref:`uefi-device-signature-variable-guid-and-variable-name`
   2.10 | 2229 - Support ISA-specific memory attributes in descriptors | :numref:`memory-types`, :numref:`efi-boot-services-getmemorymap`
   2.10 | 2247 - Support crypto agile | :numref:`cryptographic-algorithm-requirement`, :numref:`using-the-efi-variable-authentication-3-descriptor`, :numref:`using-the-efi-variable-authentication-2-descriptor`, :numref:`eap-protocol`, :numref:`efi-tls-protocols`, :numref:`firmware-os-key-exchange-creating-trust-relationships`, :numref:`authorization-process`, :numref:`pkcs7-verify-protocol`
   2.10 | 2262 - Add Memory Protection proposal - UEFI_MEMORY_ATTRIBUTE protocol | :numref:`efi-memory-attribute-protocol`
   2.10 | 2266 - Code First - Image Execution Table - revocations of hashes (Samer El-Haj-Mahmoud) | :numref:`image-execution-information-table`
   2.10 | 2271 - Introduce UEFI Conformance Profiles | :numref:`requirements`, :numref:`efi_conformance_profile_table`
   2.10 | 2277 - Code first - Uart() UEFI DevicePath binary/text confusion issue (Samer El-Haj-Mahmoud) | :numref:`text-device-node-reference`
   2.10 | 2278 - AARCH64 binding requirement for an OS calling RT services on platforms with SME | :numref:`aarch64-platforms`, :numref:`detailed-calling-convention-1`
   2.10 | 2291 - Support crypto agile - Address crypto agile compatibility | :numref:`globally-defined-variables`, :numref:`firmware-os-crypto-algorithm-exchange`
   2.10 | 2292 - Forward Control Flow Guard Instruction runtime indicator | :numref:`efi-memory-attributes-table`
   2.10 | 2313 - Add LoongArch architecture support to UEFI specification | :numref:`loongarch-platforms`
   2.10 | 2315 - Add NVM Express over Fabrics messaging device path AND NVMe Trademark updates | :numref:`block-translation-table-btt-background`, :numref:`nvme-over-fabric-namespace-device-path-format`, :numref:`nvme-over-fabric-namespace-device-path`, :numref:`nvme-over-fabric-namespace-device-path-example`, :numref:`device-node-table`, :numref:`efi-nvm-express-pass-thru-protocol-passthru`
   2.10 | 2317 - Add confidential computing extension for UEFI | :numref:`confidential-computing`
   2.10 | 2318 - Update boot requirement for RISC-V platform | :numref:`handoff-state-5`
   2.10 | 2320 - Remove EBBR Conformance profile | :numref:`efi_conformance_profile_table`
   2.10 | 2329 - Update the UEFI to Version 2.10 | :numref:`efi-system-table-1`
   2.10 | 2336 - Feedback on UEFI 2.10 draft | *sections throughout*
   2.10 | 2337 - Code First -Add LoongArch to section UEFI Images Boot Manager PCI Option ROMs and Debugger Support sections (Li Chao) | *sections throughout*
   2.10 | 2339 - Re-add RSA 4k support for UEFI 2.10 crypto agility | :numref:`firmware-os-crypto-algorithm-exchange`
   2.10 | 2342 - GetHealthStatus: Make the statement and table consistent for EFI_UNSUPPORTED for Controller Handle Null case | :numref:`efi-driver-health-protocol-gethealthstatus-protocols-uefi-driver-model`
   


**Changes in previous releases**

.. csv-table:: 
   :delim: |
   :class: longtable
   :widths: 10 58 32

   **Revision** | **Mantis # / Description** | **Affected Content**
   2.9A | 2225 - Clarify the specification requirements around processing Boot#### variable | :numref:`required-system-preparation-applications`, :numref:`global-variables`, :numref:`efi-boot-services-createeventex`
   2.9A | 2227 - Clarify NVMe device path EUI-64 byte order | :numref:`nvm-express-namespace-messaging-device-path-node`
   2.9A | 2235 - Clarify EFI_LOAD_OPTION.FilePathList[] device path definition | :numref:`load-options`
   2.9A | 2243 - Removing old references to Wired for Management (WfM) | :numref:`network-booting`, :numref:`driver-model-boot-services`, :numref:`pxe-tag-definitions-for-efi`, :ref:`referenced-specifications`, :ref:`appendix-r-glossary`
   2.9A | 2249 - Cleanup of the SI & Binary Prefixes section | :numref:`si-binary-prefixes`
   2.9A | 2251 - Clarification of DevicePath examples using 0xFF for End of HW DP | :numref:`1394-device-path`, :numref:`ps2-mouse-device-path`, :numref:`pci-root-bridge-device-path-for-a-desktop-system`, :numref:`scsi-device-path-examples`, :ref:`legacy-floppy`
   2.9A | 2252 - Clarify OS dependency on UEFI vs PI interfaces | :numref:`introduction-goals`
   2.9A | 2263 - CXL CPER updates | :numref:`cxl-protocol-error-section`
   2.9A | 2270 - Add "CPER" acronym to Appendix N | :ref:`common-platform-error-record-cper`
   2.9A | 2286 - Section header for *CHAP (using RADIUS) Authentication Node* | :numref:`chap-using-radius-authentication-node`
   2.9A | 2306 - Define Arm CPER Processor Error Types | :ref:`arm-processor-error-information-structure`
   2.9A | 2311 - Define the DevicePath argument from LoadImage as optional | :numref:`efi_boot_services-loadimage`
   2.9A | 2327 - Correcting subtype value for *REST Service Device Path* | :numref:`rest-service-device-path`
   2.9A | 2330 - Principle of Inclusive Terminology statement | :numref:`principle-of-inclusive-terminology`



.. list-table::
   :widths: 10 58 32
   :class: longtable

   * -   Revision
     -   Mantis # - Description
     -   Release Date 
   * -   2.9    
     -   1866 GetInfo() of Adapter  Information Protocol should have a  provision for IHV to return no data
     -   March 2021    
   * -   2.9    
     -   1982 Clarify the PKCS#7 SignedData  structure of  EFI_VARIABLE_AUTHENTICATION
     -   March 2021    
   * -   2.9    
     -   1986 Need a mechanism using which  browser to exit out of IHV formset  silently without any popup
     -   March 2021    
   * -   2.9
     -   1989 NVDIMM SPA Location Cookie
     -   March 2021
   * -   2.9
     -   2024 CXL CPER Records
     -   March 2021
   * -   2.9  
     -   2042 New Event Group  EFI_EVENT_GROUP\_ AFTER_READY_TO_BOOT
     -   March 2021  
   * -   2.9    
     -   2043 New Event Group  EFI_EV  ENT_GROUP_BEFORE_EXIT_BOOT_SERVICES
     -   March 2021    
   * -   2.9  
     -   2046 Add support for Key 14 & 56  for Japanese keyboard layout
     -   March 2021  
   * -   2.9  
     -   2053 Figure/Table Numbers are  Duplicated in Appendices
     -   March 2021  
   * -   2.9  
     -   2062 Table numbering to restart for  each chapter
     -   March 2021  
   * -   2.9  
     -   2065 CXL proposal for CDAT table  extraction from devices
     -   March 2021  
   * -   2.9  
     -   2093 UpdateCapsule  ScatterGatherList cache maintenance
     -   March 2021  
   * -   2.9  
     -   2129 Add DTB Configuration Table  standard GUID
     -   March 2021  
   * -   2.9
     -   2131 Clarify Console requirements
     -   March 2021
   * -   2.9  
     -   2134 Introduce unaccepted memory  type
     -   March 2021  
   * -   2.9  
     -   2155 Typo in Arm Processor CPER  Error Section
     -   March 2021  
   * -   2.9
     -   2167 CPER for CXL Component Events
     -   March 2021
   * -   2.9  
     -   2185 Declaration for UEFI 2.9  specification in the System Table
     -   March 2021  
   * -   2.9
     -   2190 Misc. spec review feedback
     -   March 2021
   * -   2.9  
     -   2199 EFI_IMAGE_EXECUTION_INFO_TABLE  references
     -   March 2021  
   * -   2.9  
     -   2200 Config tables references from  section 4.6
     -   March 2021  
   * -   2.9    
     -   2204 Typo in GUID definition for  EFI_MANAG  ED_NETWORK_SERVICE_BINDING_PROTOCOL
     -   March 2021    
   * -   2.9  
     -   2212 Incorrect cross reference to  User Information Table
     -   March 2021  
   * -   2.8 C        
     -   2117 -  E  FI_BROWSER_ACTION_REQUEST_RECONNECT  - perform the action when user  exits out of formset
     -   Jan. 2021        
   * -   2.8 C    
     -   2139 Update RISC-V UEFI  corresponding spec to align with  latest RISC-V spec
     -   Jan. 2021    
   * -   2.8 C  
     -   2155 Typo in Arm Processor CPER  Error Section
     -   Jan. 2021  
   * -   2.8 C        
     -   2158  EFI_DRIVE  R_HEALTH_PROTOCOL.GetHealthStatus()  - Driver not managing any  controller
     -   Jan. 2021        
   * -   2.8 C      
     -   2172 Revise  EFI_REDFISH_DICOVER_PROTOCOL  definitions to match the  implementation.
     -   Jan. 2021      
   * -   2.8 C  
     -   2173 Question on EFI_CAPSULE_HEADER  Flags definition
     -   Jan. 2021  
   * -   2.8 C    
     -   2184  FI_BOOT_MANAGER_POLICY_PROTOCOL  typos
     -   Jan. 2021    
   * -   2.8 C  
     -   2190 EFI_SUCCESS misspelled in five  places
     -   Jan. 2021  
   * -   
     -   
     -   
   * -   2.8 B    
     -   1926 update: corrected  EFI_SYSTEM_TABLE entries from 2_8  to 2_80
     -   May 2020    
   * -   2.8 B    
     -   1935 update: removed a space from  several references to the  EFI_JSON_CAPSULE_ID_GUID
     -   May 2020    
   * -   2.8 B  
     -   2073 Modify definition of "DPA" for  use with CXL based devices
     -   May 2020  
   * -   2.8 B
     -   2074 Memory Range typo
     -   May 2020
   * -   2.8 B  
     -   2080 Typo in N.2.2 Section  Descriptor Table 56
     -   May 2020  
   * -   2.8 B  
     -   2083 Typo in guid definition of  CCIX PER Log Error Section
     -   May 2020  
   * -   2.8 B  
     -   2088 Clarifications on caller-freed  buffers
     -   May 2020  
   * -   2.8 B        
     -   2091 Inconsistency in description  of  EFI_FIRMW  ARE_MANAGEMENT_CAPSULE_IMAGE_HEADER  structure
     -   May 2020        
   * -   2.8 B    
     -   2092 Typo in definition of PEI  Notification type in Table 269.  Error record header
     -   May 2020    
   * -   2.8 B  
     -   2095 PCI I/O attribute typos in  section 14.4 "EFI PCI I/O Protocol"
     -   May 2020  
   * -   2.8 B  
     -   UEFI Runtime Service Table  correction
     -   May 2020  
   * -   2.8 B  
     -   2096 Typo in definition of  EFI_JSON_CONFIG_DATA_ITEM
     -   May 2020  
   * -   2.8 A  
     -   1970 Security Command Protocol  change for OPAL RAID devices
     -   February 2020  
   * -   2.8 A
     -   1998 Update RISC-V related spec
     -   February 2020
   * -   2.8 A
     -   2000 JSON Capsule clarification
     -   February 2020
   * -   2.8 A  
     -   2002 Memory allocations between  ExitBootServices calls
     -   February 2020  
   * -   2.8 A
     -   2009 DMTF references in UEFI spec
     -   February 2020
   * -   2.8 A      
     -   2013 Correct  EFI  _BOOT_SERVICES.DisconnectController  contradicting info in Description
     -   February 2020      
   * -   2.8 A      
     -   2018  EFI_EDID_OVERRIDE_PROTOCOL_GET_EDID  should take an EFI_HANDLE as  ChildHandle
     -   February 2020      
   * -   2.8 A        
     -   2020  EF  I_LOADED_IMAGE_PROTOCOL.LoadOptions  does not mention it is related to  Load Options.
     -   February 2020        
   * -   2.8 A  
     -   2025 Capsule Depex Length  Declaration
     -   February 2020  
   * -   2.8 A  
     -   2026 FMP Capsule Image Header  extension
     -   February 2020  
   * -   2.8 A  
     -   2029 Add missing GUIDs in Appendix  N
     -   February 2020  
   * -   2.8 A  
     -   2030 Fix spec index to show the  Appendix chapters
     -   February 2020  
   * -   2.8 A
     -   2034 Depex added description
     -   February 2020
   * -   2.8 A  
     -   2035 Fix OUT parameters marked as  IN OUT
     -   February 2020  
   * -   2.8 A    
     -   2036 SetVariable errata: clarify  that in-place variable update is  supported
     -   February 2020    
   * -   2.8 A
     -   2038 Configuration Tables Errata
     -   February 2020
   * -   2.8 A    
     -   2041  EFI_EVENT_GROUP_EXIT_BOOT_SERVICES  Errata
     -   February 2020    
   * -   2.8 A    
     -   2050 Incomplete list of  EFI_SERVICE_BINDING_PROTOCOL  protocols
     -   February 2020    
   * -   2.8 A  
     -   2049 RuntimeServicesSupported EFI  variable should be a config table
     -   February 2020  
   * -   2.8 A  
     -   2051 Typo in Table - CPER IA32/X64  Bus Check Structure
     -   February 2020  
   * -   2.8 A  
     -   2053 Figure/Table Numbers are  Duplicated in Appendices
     -   February 2020  
   * -   2.8  
     -   1832 Extend SERIAL_IO with  DeviceTypeGuid
     -   March 2019  
   * -   2.8
     -   1834 UEFI REST EX Protocol
     -   March 2019
   * -   2.8  
     -   1853 Adding support for a REST  style formset
     -   March 2019  
   * -   2.8  
     -   1858 New Device Path for bootable  NVDIMM namespaces
     -   March 2019  
   * -   2.8  
     -   1861 New EFI_MEMORY_RANGE_CAPSULE  Descriptor
     -   March 2019  
   * -   2.8    
     -   1866 GetInfo() of Adapter  Information Protocol should have a  provision for IHV to return no data
     -   March 2019    
   * -   2.8
     -   1872 Peripheral-attached Memory
     -   March 2019
   * -   2.8  
     -   1876 Remove the EBC support  requirement
     -   March 2019  
   * -   2.8  
     -   1879 Clarification of REST (EX)  protocol
     -   March 2019  
   * -   2.8  
     -   1908 Update of uncommitted data in  the FOROM_OPEN callback
     -   March 2019  
   * -   2.8
     -   1919 Memory Cryptography Attribute
     -   March 2019
   * -   2.8
     -   1920 Redfish Discover Protocol
     -   March 2019
   * -   2.8
     -   1921 HTTPS hostname validation
     -   March 2019
   * -   2.8    
     -   1924 Update to  EF  I_REST_EX_PROTOCOL.AsyncSendReceive
     -   March 2019    
   * -   2.8  
     -   1925 Clarify requirement of REST  related protocols
     -   March 2019  
   * -   2.8
     -   1926 New UEFI Spec Revision --> 2.8
     -   March 2019
   * -   2.8
     -   1935 UEFI JSON Capsule Support
     -   March 2019
   * -   2.8  
     -   1936 ResetSystem - support  ResetData for all status scenarios.
     -   March 2019  
   * -   2.8
     -   1937 Behavior of default values
     -   March 2019
   * -   2.8  
     -   1941 New EFI REST JSON Structure  Protocol
     -   March 2019  
   * -   2.8  
     -   1942 Adding dependency expression  capability into FMP type capsules
     -   March 2019  
   * -   2.8    
     -   1947 Keyword strings of  Configuration Keyword Handler  Protocol Enhancements
     -   March 2019    
   * -   2.8  
     -   1953 Add document version#  conventions
     -   March 2019  
   * -   2.8      
     -   1954 set (\*Attributes) when  GetVariable() returns  EFI_BUFFER_TOO_SMALL and Attributes  is non-NULL
     -   March 2019      
   * -   2.8  
     -   1956 Platform to honor  ActionRequest for Action changing
     -   March 2019  
   * -   2.8  
     -   1961 Add EFI_UNSUPPORTED to  EFI_RUNTIME_SERVICES calls
     -   March 2019  
   * -   2.8  
     -   1966 Add new capsule processing  error codes
     -   March 2019  
   * -   2.8  
     -   1974 Add new CCIX PER Log Error  Section to appendix
     -   March 2019  
   * -   2.8    
     -   1996 Firmware Processing of the  Capsule Identified by  EFI_JSON_CAPSULE_ID_GUID
     -   March 2019    
   * -   2.7B  
     -   1773 Clarify The EFI System Table  entry for capsule image
     -   March 2019  
   * -   2.7B  
     -   1801 ExtractConfig() format may  change when called multiple times
     -   March 2019  
   * -   2.7B  
     -   1835 Misleading / unclear statement  about EFI-bootability of UDF media
     -   March 2019  
   * -   2.7B  
     -   1838 RGB/BGR Contradiction in 2.7  GOP
     -   March 2019  
   * -   2.7B  
     -   1841 BluetoothLE ECR - support  autoreconnect
     -   March 2019  
   * -   2.7B  
     -   1842 BluetoothLE ECR - Add missing  ConnectionCompleteCallback
     -   March 2019  
   * -   2.7B
     -   1843 HTTP Example Code Update
     -   March 2019
   * -   2.7B  
     -   1844 Replace obsoleted RFC number  with new number for TCP
     -   March 2019  
   * -   2.7B    
     -   1845 Clarification on AIP types  "Network boot" and "SAN MAC  Address"
     -   March 2019    
   * -   2.7B
     -   1846 EFI_LOAD_FILE2 requirement
     -   March 2019
   * -   2.7B  
     -   1865 Adding clarification in  EFI_NOT_READY for ReadKeyStrokeEx()
     -   March 2019  
   * -   2.7B  
     -   1869 Clarify FMP buffer too small  behavior
     -   March 2019  
   * -   2.7B  
     -   1874 Add RFC3021 to reference in  uefi.org
     -   March 2019  
   * -   2.7B  
     -   1875 Clarify platform specific  elements in chapter 2.6.2
     -   March 2019  
   * -   2.7B  
     -   1878 Errata - Make DHCP server  optional for HTTP boot
     -   March 2019  
   * -   2.7B  
     -   1880 Arm binding EL2 register state  clarification
     -   March 2019  
   * -   2.7B  
     -   1890 EfiMemoryMappedIO Usage  Clarification
     -   March 2019  
   * -   2.7B    
     -   1897 Clarification on mapping of  UEFI memory attributes to ARM  memory types and paging attributes
     -   March 2019    
   * -   2.7B    
     -   1899 Errata: Clarify  EFI_INVALID_PARAMETER for  FMP->GetImageInfo()
     -   March 2019    
   * -   2.7B
     -   1901 GPT Protective MBR description
     -   March 2019
   * -   2.7B
     -   1902 CapsuleImageSize Clarification
     -   March 2019
   * -   2.7B
     -   1903 Root Directory File Name
     -   March 2019
   * -   2.7B  
     -   1906 ACPI Table Pointer  Installation
     -   March 2019  
   * -   2.7B  
     -   1908 Update of uncommitted data in  the FOROM_OPEN callback
     -   March 2019  
   * -   2.7B  
     -   1923 Syntax error in EFI iSCSI  Initiator Name Protocol
     -   March 2019  
   * -   2.7B  
     -   1957 Request to add status code  EFI_DEVICE_ERROR for ExtractConfig
     -   March 2019  
   * -   2.7B  
     -   1964 Print disclaimer for all  future UEFI specs
     -   March 2019  
   * -   2.7B  
     -   1987 incorrect VLAN_CONFIG_SET  function definition
     -   March 2019  
   * -   2.7A    
     -   1830 Label Protocol -  EFI_NVDIMM_LABEL_FLAGS_LOCAL  definition needs to be updated
     -   August 2017    
   * -   2.7A    
     -   1829 Label Protocol Section -  Missing define for  EFI_NVDIMM_LABEL_FLAGS_UPDATING
     -   August 2017    
   * -   2.7A    
     -   1823 Modifications to the examples  of the PCI Option ROM image  combinations
     -   August 2017    
   * -   2.7A  
     -   1822 UEFI 2.7 Organization chapter  duplicated
     -   August 2017  
   * -   2.7A  
     -   1821 Modify the requirement to  enable PCI Bus Mastering
     -   August 2017  
   * -   2.7A    
     -   1817 NVDIMM Label Protocol -  SetCookie SerialNumber needs to be  UINT32 NOT UINT64
     -   August 2017    
   * -   2.7A  
     -   1816 Clarification of Using  HttpConfigData in HTTP protocol
     -   August 2017  
   * -   2.7A    
     -   1815 OpenProtocol() /  EFI_ALREADY_STARTED should output  existent Interface
     -   August 2017    
   * -   2.7A  
     -   1808 Clarification of using option  43 in PXE v2.1
     -   August 2017  
   * -   2.7  
     -   1779 Adjusting UEFI version to UEFI  2.7
     -   April 2017  
   * -   2.7
     -   1771BluetoothLE minor fix
     -   April 2017
   * -   2.7
     -   1762 UEFI UFS DEVICECONFIG Protocol
     -   April 2017
   * -   2.7
     -   1751 Update DNS Device Path
     -   April 2017
   * -   2.7  
     -   1750 Add new data type to EFI  Supplicant Protocol
     -   April 2017  
   * -   2.7
     -   1745 NVDIMM Label Protocol
     -   April 2017
   * -   2.7  
     -   1744 NVDIMMBlock Translation Table  (BTT) Protocol {NewChapter}
     -   April 2017  
   * -   2.7
     -   1730 HII Popup Protocol
     -   April 2017
   * -   2.7
     -   1726 Host and I/O defense
     -   April 2017
   * -   2.7    
     -   1720 Have Partition driver publish  addition information for MBR/GPT  partition types.
     -   April 2017    
   * -   2.7  
     -   1719 Add EFI HTTP Boot Callback  Protocol
     -   April 2017  
   * -   2.7    
     -   1718 Allow SetData to clear  configuration in  Ip4Config2/Ip6Config Protocol
     -   April 2017    
   * -   2.7
     -   1716 Add BluetoothLE ECR
     -   April 2017
   * -   2.7
     -   1711 Firmware Error Record Update
     -   April 2017
   * -   2.7  
     -   1707 Clarification of Private  Authenticated Variables
     -   April 2017  
   * -   2.7  
     -   1701 Add wildcard support to  RegisterKeyNotify
     -   April 2017  
   * -   2.7  
     -   1690 Reset Notification Protocol  Update
     -   April 2017  
   * -   2.7  
     -   1689 Secure Boot with Externally  Managed Configuration
     -   April 2017  
   * -   2.7  
     -   1685 Key Management Services (KMS)  Protocol Enhancement
     -   April 2017  
   * -   2.7
     -   1672 UEFI Variable Enhancements
     -   April 2017
   * -   2.7  
     -   1654 New AIP Information block for  wireless NIC
     -   April 2017  
   * -   2.7
     -   1652 Add DNS device path node
     -   April 2017
   * -   2.7
     -   1647 UEFI binding for RISC-V
     -   April 2017
   * -   2.7  
     -   1641 Simplify SecureBoot Revocation  and Usage of VerifySignature
     -   April 2017  
   * -   2.7    
     -   1641 Simplify Secure Boot  Revocation and Usage of  VerifySignature
     -   April 2017    
   * -   2.7  
     -   1627 Support ASCII RegEx Patterns  in EFI_REGULAR_EXPRESSION_PROTOCOL
     -   April 2017  
   * -   2.7  
     -   1627 EFI regular expression syntax  type definitions
     -   April 2017  
   * -   2.7  
     -   1623 New EFI_HTTP_STATUS_CODE enum  for 308 Permanent Redirect
     -   April 2017  
   * -   2.7  
     -   1623 New EFI_HTTP_STATUS_CODE enum  for 308 Permanent Redirect
     -   April 2017  
   * -   2.6B  
     -   1772 Clarify EFI_NOT_READY in Media  State of AIP
     -   April 2017  
   * -   2.6B  
     -   1767 Incorrect structure definition  for EFI_IFR_RESET_BUTTON_OP
     -   April 2017  
   * -   2.6B  
     -   1742 Clairfy PK enrolling in user  mode
     -   April 2017  
   * -   2.6B    
     -   1741 The memory map  returnedByBS->GetMemoryMap()  mayContain impossible values.
     -   April 2017    
   * -   2.6B
     -   1739 typos -Broken references link.
     -   April 2017
   * -   2.6B  
     -   1729Cleanup of ACPI 2.0 references  in UEFI spec
     -   April 2017  
   * -   2.6B  
     -   1708 Typos in Imge Decode and Image  Ex Protocols
     -   April 2017  
   * -   2.6B    
     -   1700 Align ACPI descriptor  definitions in PCI I/O and PCI  RootBridge I/O
     -   April 2017    
   * -   2.6B  
     -   1698 Update to Mantis 1613 -  GetNextVariable
     -   April 2017  
   * -   2.6B  
     -   1691 Remove/Deprecate SMM  Communication ACPI Table
     -   April 2017  
   * -   2.6B
     -   1682 HII Protocol StatusCodes
     -   April 2017
   * -   2.6B  
     -   1678 Simplify the ACPI Table GUID  declarations
     -   April 2017  
   * -   2.6B
     -   1675 section 30.5.1 typo
     -   April 2017
   * -   2.6B    
     -   1668 Duplicate GUID issue -  mustChange the Image Decoder  Protocol GUID
     -   April 2017    
   * -   2.6B
     -   1655 HTTP errata inConfigure()
     -   April 2017
   * -   2.6B  
     -   1653 Incorrect errorCode value in  MTFTP6
     -   April 2017  
   * -   2.6B    
     -   1634 Update to the  EFI_SIMPLE_TEXT_INPUT_PROTOCOL TPL  restriction
     -   April 2017    
   * -   2.6B  
     -   1629 Errata in GetVariable  description
     -   April 2017  
   * -   2.6B    
     -   1625 Clarification of HTTPBoot wire  protocol "HTTPClient" VendorClass  Option
     -   April 2017    
   * -   2.6B  
     -   1624 Fix spelling typo in  EFI_HTTP_STATUS_CODE
     -   April 2017  
   * -   2.6B
     -   1613 GetNextVariableName Errata
     -   April 2017
   * -   2.6B
     -   1612 ResetSystem Errata
     -   April 2017
   * -   2.6B    
     -   1609 UEFI Errata - Address Security  problems in the Pkcs7Verify  Protocol
     -   April 2017    
   * -   2.6B
     -   1608 Enhance EFI_IFR_NUMERIC (Step)
     -   April 2017
   * -   2.6B  
     -   1586 Errors in appendix N for ARM  ProcessorContext Information
     -   April 2017  
   * -   2.6B
     -   1584 WIFI errata
     -   April 2017
   * -   2.6B
     -   1580 Correct some typos
     -   April 2017
   * -   2.6B  
     -   1559 Clarify return value for NULL  pointer in LocateProtocol() API
     -   April 2017  
   * -   2.6B  
     -   1557 secureBoot and auth variable  errata
     -   April 2017  
   * -   2.6B
     -   1556 HTTPv6Boot DHCP Options Errata
     -   April 2017
   * -   2.6B  
     -   1555 USB Function port protocol  errata
     -   April 2017  
   * -   2.6B
     -   1554 fix to ecr 1539
     -   April 2017
   * -   2.6B
     -   1553 os recoveryBoot option errata
     -   April 2017
   * -   2.6B  
     -   1551 EFIBluetoothConfiguration  Protocol Errata
     -   April 2017  
   * -   2.6B    
     -   1550 Replace FTP4 dataCallback  pointer-to-function-pointer with  regular function pointer
     -   April 2017    
   * -   2.6A      
     -   SameContent as version 2.6,But with  the Adobe "accessibility" feature  activated so text-to-speech will  work.
     -   December 2016      
   * -   2.6  
     -   1548ClarifyBoot procedure when file  name is absent2.
     -   January, 2016  
   * -   2.6  
     -   1547Clarify requirements for  setting the PK variable.
     -   January, 2016  
   * -   2.6
     -   1544 DNS lookup API spelling
     -   January, 2016
   * -   2.6  
     -   1543 ip4/6Config policy errata/2.6  update
     -   January, 2016  
   * -   2.6
     -   1542 UEFI 2.6 supplicant errata
     -   January, 2016
   * -   2.6
     -   1539 New EFI_HTTP_ERROR StatusCode
     -   December, 2015
   * -   2.6
     -   1538 UEFI TLS errata
     -   December, 2015
   * -   2.6    
     -   1536 UEFI 2.6 Errata : IMAGE EX  Protocol and EFI HII Image Decoder  protocol Errata
     -   December, 2015    
   * -   2.6  
     -   1534 EditorialComments against 2.6  Final Draft
     -   December, 2015  
   * -   2.6
     -   1533Bugs in the HTTP usage example
     -   December, 2015
   * -   2.6
     -   1523Comments against 2.6 Draft
     -   December, 2015
   * -   2.6  
     -   1522 AArch64Bindings AlignmentBit  errata
     -   December, 2015  
   * -   2.6  
     -   1521Comment against UEFI.next draft  - M1479
     -   December, 2015  
   * -   2.6  
     -   1519 Version for the next UEFI spec  is...
     -   December, 2015  
   * -   2.6
     -   1518Comments against 2.6 Draft
     -   December, 2015
   * -   2.6  
     -   1516 EditorialComments against 2.6  Draft
     -   December, 2015  
   * -   2.6        
     -   1509  EFI_PLATFO  RM_TO_DRIVER_CONFIGURATION\_ PROTOCOL  Response to unsupported  ParameterTypeGuid
     -   December, 2015        
   * -   2.6    
     -   1508 Lack of flexibility and  realism in exception levelChoice  whenCalling runtime services
     -   December, 2015    
   * -   2.6  
     -   1507 Insufficient qualification of  page attributes for AArch64
     -   December, 2015  
   * -   2.6    
     -   1502 PCI IO Define how to use the  Address Translation Offset for  systems that are not mapped 1:1
     -   November, 2015    
   * -   2.6    
     -   1501 Define the usage of the  "Address Space Granularity" field  is defined in the PCI Root IO
     -   November, 2015    
   * -   2.6    
     -   1496Bad table reference in 13.2  EFI_PCI_ROOT  _BRIDGE_IO_PROTOCOL.Configuration()
     -   November, 2015    
   * -   2.6  
     -   1494 Errata against UEFI 2.5  Properties Table
     -   November, 2015  
   * -   2.6  
     -   1493 Updates to the  SD_MMC_PASS_THRU interface
     -   November, 2015  
   * -   2.6  
     -   1492 wireless macConnection  protocol II errata
     -   November, 2015  
   * -   2.6
     -   1491 supplicant errata
     -   November, 2015
   * -   2.6  
     -   1480 Refine Progress description in  EFI_KEYWORD_HANDLER_PROTOCOL
     -   November, 2015  
   * -   2.6  
     -   1479 UEFI Properties  TableClarification
     -   November, 2015  
   * -   2.6  
     -   1471 SD/eMMC PassThru Protocol  update (follow up to mantis 1376)
     -   November, 2015  
   * -   2.6    
     -   1467 New API -  EFI\_  WIRELESS_MAC_CONNECTION_II_PROTOCOL
     -   November, 2015    
   * -   2.6
     -   1466 UEFI Ram disk protocol
     -   November, 2015
   * -   2.6
     -   1452 Minor edits to 0001409
     -   November, 2015
   * -   2.6  
     -   1414 Generalisation ofCommunication  method in Appendix O
     -   November, 2015  
   * -   2.6  
     -   1409 EFI HII ImageEX protocol and  EFI HII Image Decoder protocols
     -   November, 2015  
   * -   2.6    
     -   1408 EFI HII Font EX protocol and  EFI HII Font Glyph Generator  protocols
     -   November, 2015    
   * -   2.6  
     -   1402 Add  EFI_BROWSER_ACTION_SUBMITTED
     -   November, 2015  
   * -   2.6  
     -   1383 Adding an EraseBlocks()  function to a new protocol
     -   November, 2015  
   * -   2.6
     -   1376 SD/eMMC PassThru Protocol
     -   November, 2015
   * -   2.6
     -   1357 ARMCPER extensions
     -   November, 2015
   * -   2.5A  
     -   1481 new networkConfig2 protocol  data structure has a magic number
     -   October 2015  
   * -   2.5A  
     -   1477 AllowCloseEvent toBeCalled  within the Notification Function
     -   October 2015  
   * -   2.5A      
     -   1476 Update to Indicate  thatCloseEvent  UnregistersCorresponding Protocol  Notification Registrations
     -   October 2015      
   * -   2.5A
     -   1472 ATA Pass Thru Errata
     -   October 2015
   * -   2.5A  
     -   1469 UNDI Errata - add more  statistics
     -   October 2015  
   * -   2.5A  
     -   1468 Errata on UEFI Supplicant  protocol
     -   October 2015  
   * -   2.5A
     -   1451 Memory MapConsistency
     -   October 2015
   * -   2.5A  
     -   1441 UEFI2.5A – UNDI  ProtocolClarification
     -   October 2015  
   * -   2.5A
     -   1426 UEFI 2.5 typo
     -   October 2015
   * -   2.5A  
     -   1424 Incorrect link in Section 22.1  FMP GetImageInfo()
     -   October 2015  
   * -   2.5A
     -   1421 Misc HTTP API typos
     -   October 2015
   * -   2.5A    
     -   1420  Get  NextHighMonotonicCountClarification
     -   October 2015    
   * -   2.5A  
     -   1419 Supplicant protocol using same  GUID as TLS protocol
     -   October 2015  
   * -   2.5A
     -   1418 Inconsistent issues in DNS
     -   October 2015
   * -   2.5A  
     -   1417 Add HttpMethodMax to  EFI_HTTP_METHOD enum
     -   October 2015  
   * -   2.5A
     -   1410Clarifications in appendix O
     -   October 2015
   * -   2.5A  
     -   1407 Networking errata -  EFI_HTTP_STATUS typos
     -   October 2015  
   * -   2.5A  
     -   1405 Errata in table 271 in  Appendix O
     -   October 2015  
   * -   2.5A    
     -   1399 Clarification for  EFI_BROWSER_ACTION\_ REQUEST_RECONNECT
     -   October 2015    
   * -   2.5A  
     -   1398 Errata update to the runtime  GetVariable operation documentation
     -   October 2015  
   * -   2.5A
     -   1388 Missed memory type fixes
     -   October 2015
   * -   2.5A  
     -   1381 Remove informativeContent in  12.6.1
     -   October 2015  
   * -   2.5A    
     -   1365 7.4 Virtual Memory Services  lists Section 2.3.2 through Section  2.3.4. incorrectly
     -   October 2015    
   * -   2.5A
     -   1363 Short form URI device path
     -   October 2015
   * -   2.5A  
     -   1209 UEFI networking APIChapter 2.6  requirements errors
     -   October 2015  
   * -   2.5A
     -   
     -   October 2015
   * -   2.5  
     -   1364 Extend supplicant data type  for EAP
     -   April, 2015  
   * -   2.5
     -   1362 HTTPBoot typos/bugs
     -   April, 2015
   * -   2.5  
     -   1360 Vendor Range for UEFI memory  Types
     -   April, 2015  
   * -   2.5    
     -   1358 v2.5 amendment and v2.4 errata  (missed implementation of Mantis  1089)
     -   April, 2015    
   * -   2.5
     -   1353 SATA Device Path Node Errata
     -   April, 2015
   * -   2.5
     -   1352 Errata for 1263 and 1227
     -   
   * -   2.5
     -   1350 Keyword Strings Errata
     -   April, 2015
   * -   2.5      
     -   1348 ERRATA - Section 10.12  EFI  _ADAPTER_INFORMATION_PROTOCOLCustom  Types
     -   April, 2015      
   * -   2.5
     -   1347Boot Manager Policy Errata
     -   April, 2015
   * -   2.5
     -   1346 Mantis 1288 Errata
     -   April, 2015
   * -   2.5
     -   1345 EFI_USB2_HC_PROTOCOL Errata
     -   April, 2015
   * -   2.5  
     -   1342 DNS6 - friendly amendment for  reviewBy USWG
     -   April, 2015  
   * -   2.5  
     -   1341 DNS4 - friendly amendment toBe  reviewedBy USWG
     -   April, 2015  
   * -   2.5  
     -   1339 Errata in section 7.2.3.2  Hardware Error Record Variables
     -   April, 2015  
   * -   2.5    
     -   1309 Disallow  EFI_VARIABLE_AUTHENTICATION from  SecureBoot Policy Variables
     -   April, 2015    
   * -   2.5    
     -   1308 Fix typo's found in the  final/published UEFI 2.4 ErrataB  spec
     -   February, 2015    
   * -   2.5      
     -   1304 Add  IMA  GE_UPDATABLE_VALID_WITH_VENDOR\_ CODE  to FMPCheck image
     -   February, 2015      
   * -   2.5  
     -   1303 Update the UEFI version to  reflect new revision
     -   February, 2015  
   * -   2.5        
     -   1288 The Macro definitionConflict  in  EFI_SIMPLE\_  TEXT_OUTPUT_PROTOCOL.SetAttribute()  in UEFI 2.4B
     -   February, 2015        
   * -   2.5    
     -   1287 Errata: EFI Driver Supported  EFI Version not matching the spec  revision
     -   February, 2015    
   * -   2.5  
     -   1269Configuration Routing Protocol  andConfiguration String Updates
     -   February, 2015  
   * -   2.5
     -   1268 RAM Disk UEFI Device Path Node
     -   February, 2015
   * -   2.5  
     -   1266 UEFI.Next Feature - IP_CONFIG2  Protocol
     -   February, 2015  
   * -   2.5  
     -   1263Customized Deployment of  SecureBoot
     -   February, 2015  
   * -   2.5      
     -   1257Correct the typedef definitions  for  EFI_BOOT_SERVI  CES/EFI_RUNTIME_SERVICES--Reiterate
     -   February, 2015      
   * -   2.5
     -   1255 UFS Device Path Node Length
     -   February, 2015
   * -   2.5
     -   1254 SD Device Path
     -   February, 2015
   * -   2.5    
     -   1251  EFI_REGULAR_EXPRESSION_PROTOCOL and  EFI_IFR_MATCH2 HII op-code
     -   February, 2015    
   * -   2.5  
     -   1244 sections of the spec  mis-arranged
     -   February, 2015  
   * -   2.5  
     -   1234 UEFI.Next feature - SmartCard  edge protocol
     -   February, 2015  
   * -   2.5  
     -   1227 UEFI.Next feature - Platform  recovery
     -   February, 2015  
   * -   2.5  
     -   1224 UEFI.Next - Adding support for  No executable data areas
     -   February, 2015  
   * -   2.5  
     -   1223 UEFI.Next networking features  -Chapter 2.6 requirements
     -   February, 2015  
   * -   2.5  
     -   1222 UEFI.Next feature -BMC/Service  Processor Device Path
     -   February, 2015  
   * -   2.5  
     -   1221 UEFI.Next feature - REST  Protocol
     -   February, 2015  
   * -   2.5
     -   1220 UEFI.Next feature -Bluetooth
     -   February, 2015
   * -   2.5  
     -   1219 UEFI.Next Feature - UEFI TLS  API
     -   February, 2015  
   * -   2.5  
     -   1218 UEFI.Next feature - EAP2  Protocol
     -   February, 2015  
   * -   2.5  
     -   1217 UEFI.Next feature - WIFI  support
     -   February, 2015  
   * -   2.5  
     -   1216 UEFI.next feature - DNS  version 6
     -   February, 2015  
   * -   2.5  
     -   1215 UEFI.Next feature - DNS  version 4
     -   February, 2015  
   * -   2.5
     -   1214 UEFI.Next feature - HTTPBoot
     -   February, 2015
   * -   2.5  
     -   1213 UEFI.Next feature - HTTP  helper API
     -   February, 2015  
   * -   2.5
     -   1212 UEFI.Next feature - HTTP API
     -   February, 2015
   * -   2.5  
     -   1204 new UEFI USB Function I/O  Protocol addition to the UEFI spec
     -   February, 2015  
   * -   2.5  
     -   1201 Exposing Memory Redundancy to  OSPM
     -   February, 2015  
   * -   2.5  
     -   1199 Add NVM Express Pass Thru  Protocol
     -   February, 2015  
   * -   2.5  
     -   1191 Add new SMBIOS3_TABLE_GUID in  EFI_CONFIGURATION_TABLE
     -   February, 2015  
   * -   2.5  
     -   1186 AArch64BindingClarifications  and errata
     -   February, 2015  
   * -   2.5    
     -   1183 New Protocol with 2 Function  for PKCS7 Signature Verification  Services
     -   February, 2015    
   * -   2.5  
     -   1174 errata - Error in  EFI_IFR_PASSWORD logic flowchart
     -   February, 2015  
   * -   2.5
     -   1167 Persistent Memory Type support
     -   February, 2015
   * -   2.5
     -   1166 hash 2 protocol errata
     -   February, 2015
   * -   2.5  
     -   1163 InlineCryptographic Interface  Protocol proposal
     -   February, 2015  
   * -   2.5  
     -   1159 Proposal for System Prep  Applications
     -   February, 2015  
   * -   2.5  
     -   1158 errata -Boot  managerClarification
     -   February, 2015  
   * -   2.5
     -   1147--REDACT
     -   February, 2015
   * -   2.5
     -   1121 IPV6 support from UNDI
     -   February, 2015
   * -   2.5
     -   1109 SmartCard Reader
     -   February, 2015
   * -   2.5  
     -   1103 Longer term NewCPER Memory  Section
     -   February, 2015  
   * -   2.5  
     -   1091Clarification of handle to host  FMP
     -   February, 2015  
   * -   2.5  
     -   1090 ESRT: EFI System Resource  Table andComponent firmware updates
     -   February, 2015  
   * -   2.5
     -   1071 New EFI_HASH2_PROTOCOL
     -   February, 2015
   * -   2.4C    
     -   1308 Fix typo's found in the  final/published UEFI 2.4 ErrataB  spec
     -   January 2015    
   * -   2.4C    
     -   1287 Errata: EFI Driver Supported  EFI Version not matching the spec  revision
     -   January 2015    
   * -   2.4C      
     -   1257Correct the typedef definitions  for  EFI\_  _BOOT_SERVICES/EFI_RUNTIME_SERVICES
     -   January 2015      
   * -   2.4C  
     -   1244 sections of the spec  misarranged
     -   January 2015  
   * -   2.4C
     -   1211 EFI_LOAD_OPTION Definition
     -   January 2015
   * -   2.4C  
     -   1209 Errata - UEFI networking  APIChapter 2.6 requirements
     -   January 2015  
   * -   2.4C
     -   1205 Errata for Hii Set item
     -   January 2015
   * -   2.4C  
     -   1200 Universal Flash Storage (UFS)  Device Path
     -   January 2015  
   * -   2.4C    
     -   1198  EFI\_  ATA_PASS_THRU_PROTOCOLClarification
     -   January 2015    
   * -   2.4C  
     -   1194 Add  EFI_IFR_FLAG_RECONNECT_REQUIRED
     -   January 2015  
   * -   2.4C
     -   1192Cleanup GUID formatting issues
     -   January 2015
   * -   2.4C  
     -   1186 AArch64BindingClarifications  and errata
     -   January 2015  
   * -   2.4C
     -   1185 errata - tcp api
     -   January 2015
   * -   2.4C
     -   1184 errata - snp modeClarification
     -   January 2015
   * -   2.4C  
     -   1182 Errata - UEFI URI Device path  issue
     -   January 2015  
   * -   2.4C  
     -   1174 errata - Error in  EFI_IFR_PASSWORD logic flowchart
     -   January 2015  
   * -   2.4C
     -   1173 EFI_IFR_NUMERIC Errata
     -   July 11, 2014
   * -   2.4C  
     -   1172 EfiACPIMemoryNVS definition  missing S4
     -   July 11, 2014  
   * -   2.4C
     -   1170 Errata pxeBc apiClarifiation
     -   July 11, 2014
   * -   2.4C  
     -   1169 Errata - volatile networking  variableCleanup
     -   July 11, 2014  
   * -   2.4C
     -   1168 MTFTP Errata
     -   July 11, 2014
   * -   2.4C
     -   1165 Option rom layout errata
     -   July 11, 2014
   * -   2.4C    
     -   1162 Typo in  ReinstallProtocolInterface() EFI  1.10 Extension section
     -   July 11, 2014    
   * -   2.4C  
     -   1150 Missing LineBreakCharacter  (HII Errata)
     -   July 11, 2014  
   * -   2.4C      
     -   1147  EFI_USB2_H  C_PROTOCOL.AsyncInterruptTransfer()  Errata
     -   July 11, 2014      
   * -   2.4C  
     -   1141 UEFI errata - ia32/x64 vector  register management
     -   July 11, 2014  
   * -   2.4C  
     -   1140UEFI Errata - image execution  info table
     -   July 11, 2014  
   * -   2.4C  
     -   1139 UEFI Errata on the storage  securityCommand protocol
     -   July 11, 2014  
   * -   2.4C  
     -   1066 Errata--reference to missing  table (90) removed
     -   July 11, 2014  
   * -   2.4C  
     -   1043 Ability to refresh the entire  form [newContent]
     -   July 11, 2014  
   * -   2.4C  
     -   1042 AddBrowser Action Request  "reconnect"
     -   July 11, 2014  
   * -   2.4B
     -   1146 Typos andBroken links
     -   April 17, 2014
   * -   2.4B  
     -   1137 Typographic errors in the 2.4  ErrataB draft
     -   April 16, 2014  
   * -   2.4B  
     -   1128 URI device path node  redux--supersedes (defunct) 1119
     -   April 4, 2014  
   * -   2.4B    
     -   1127 USB Errata - unnecessary  restriction on UEFI interrupt  transfer types
     -   March 27, 2014    
   * -   2.4B  
     -   1124 Adding text description for  NVMe device node
     -   March 27, 2014  
   * -   2.4B          
     -   1122Correct misleading language in  the UEFI 2.4a specification about  the  EFI_ADAPTER_INFORMATION_PROTOCOL.E  FI_ADAPTER_INFO_GET_SUPPORTED_TYPES  function
     -   March 27, 2014          
   * -   2.4B    
     -   1120 Make time stamp  handlingConsistent around all of  the networking API’s
     -   March 27, 2014    
   * -   2.4B    
     -   1118 Network Performance  EnhancementsConcerning Volatile  Variables
     -   March 27, 2014    
   * -   2.4B      
     -   1115Clarification on the usage of  XMM/FPU instructions from within a  UEFI Runtime Service on an x64  processor
     -   March 27, 2014      
   * -   2.4B    
     -   1111 Errors in  DisconnectController() returnCode  descriptions
     -   March 27, 2014    
   * -   2.4B  
     -   1101 Errata –  ReinstallProtocolInterface
     -   March 27, 2014  
   * -   2.4B  
     -   1092Clarification to PCI Option ROM  Driver Loading Description
     -   March 27, 2014  
   * -   2.4B  
     -   1085 Error--added in missing text  approved for 2.4A
     -   April 17, 2014  
   * -   2.4B  
     -   1014 HIIConfig Access Protocol  Errata
     -   April 3, 2014  
   * -   2.4 A  
     -   1089 Short-termCPER Memory Section  errata
     -   Nov. 14, 2013  
   * -   2.4 A  
     -   1088 Add revision #define to  EFI_FILE_PROTOCOL
     -   Nov. 6, 2013  
   * -   2.4 A  
     -   1085 Issues with Interactive  password
     -   Nov.14, 2013  
   * -   2.4 A  
     -   1082 Mistake in 2.3.5.1 / 2.3.6.2  Handoff State
     -   Nov. 6, 2013  
   * -   2.4 A  
     -   1081 Update Install Table protocol  to deal with duplicate tables
     -   Nov. 6, 2013  
   * -   2.4 A  
     -   1079 UEFI 2.4: Remove repetitive  "the" (typo)
     -   Nov. 6, 2013  
   * -   2.4 A  
     -   1078 Adjust some text for handling  EFI_BROWSER_ACTION_CHANGING
     -   Nov. 6, 2013  
   * -   2.4 A  
     -   1077 Fix wording in  EVT_SIGNAL_EXIT_BOOT_SERVICES
     -   Nov. 6, 2013  
   * -   2.4 A
     -   1076 typo in UEFI v2.3.1d and v2.4
     -   Nov. 6, 2013
   * -   2.4 A    
     -   1075Clarifications to Table 88.  Device Node Table (Device Node to  TextConversion)
     -   Nov. 6, 2013    
   * -   2.4 A  
     -   1074 AddClarifications on DMA  requirements for PCI_IO
     -   Nov. 6, 2013  
   * -   2.4 A  
     -   1073 Add requirement for  EFI_USB_IO_PROTOCOL
     -   Nov. 6, 2013  
   * -   2.4 A  
     -   1066 Errata - ISCSI IPV6 Root  PathClarification
     -   Nov. 6, 2013  
   * -   2.4 A
     -   1064 AIP Errata
     -   Nov. 6, 2013
   * -   2.4 A  
     -   1063Correction to GPT expression  for SizeofPartitionEntry
     -   Nov. 6, 2013  
   * -   2.4 A  
     -   1062 EFI_CERT_X509_GUID does not  specify theCertificate encoding
     -   Nov. 6, 2013  
   * -   2.4 A    
     -   1061 UEFI 2.4 section 2.6.2 and  2.6.3 don't use protocol  hyperlinksConsistently
     -   Nov. 6, 2013    
   * -   2.4 A  
     -   1060 SlightClarification to FMP  Authentication Requirments
     -   Nov. 6, 2013  
   * -   2.4 A  
     -   1059Clarification of a return  statusCode of HASH protocol
     -   Nov. 6, 2013  
   * -   2.4 A  
     -   1058Correct mistake in the system  table revision
     -   Nov. 6, 2013  
   * -   2.4 A        
     -   1056 text modification to  definition of  EF  I_FIRMWARE_IMAGE_DESCRIPTOR_VERSION  2
     -   Nov. 6, 2013        
   * -   2.4 A
     -   1055 Disk IO 2 errata
     -   Nov. 6, 2013
   * -   2.4 A  
     -   1054 Deprecate 6 Hash Algorithms  with inconsistent usage
     -   Nov. 6, 2013  
   * -   2.4 A    
     -   1053 Reduce Name space ofCapsule  Result variable to increase  performance
     -   Nov. 6, 2013    
   * -   2.4 A    
     -   1035 PCI Option ROM Errata    (five figures)
     -   Nov. 6, 2013    
   * -   2.4  
     -   997 Driver Health Protocol  errorCodes
     -   April 25, 2013  
   * -   2.4  
     -   993 (original ticket--supersededBy  1026)
     -     
   * -   2.4  
     -   992 Adapter Information Protocol  (AIP)
     -   April 25, 2013  
   * -   2.4  
     -   991 Greater than 256 NICs support  on UNDI
     -   April 25, 2013  
   * -   2.4  
     -   968 HII Forms op-code for  displaying a warning message
     -   April 25, 2013  
   * -   2.4
     -   966 Spec typos
     -   April 25, 2013
   * -   2.4  
     -   964 Disk IO 2 Protocol to support  Async IO
     -   April 25, 2013  
   * -   2.4  
     -   963 Add new device path node NVM  Express devices
     -   April 25, 2013  
   * -   2.4  
     -   956 Require network drivers to  return EFI_NO_MEDIA
     -   April 25, 2013  
   * -   2.4    
     -   946 ForbidCreation of non-spec  variables in EFI_GLOBAL_VARIABLE  namespace
     -   April 25, 2013    
   * -   2.4  
     -   920 Add a variable for indicating  out ofBand key modification
     -   April 25, 2013  
   * -   2.4    
     -   905 Need more granularity in  EFI_RESET_TYPE to support platform  specific resets
     -   April 25, 2013    
   * -   2.4  
     -   1052 UEFI 2.4 Draft April 25th  -Corrections to ARM sections
     -   May 16, 2013  
   * -   2.4  
     -   1050 2.4 Draft April 25 has missing  text for ECR 1009
     -   May 16, 2013  
   * -   2.4  
     -   1049 2.4 Draft April 25 has missing  text for ECR 1008
     -   May 16, 2013  
   * -   2.4  
     -   1048Comment against UEFI 2.4 - NVMe  related
     -   May 16, 2013  
   * -   2.4  
     -   1047Comment on Feb 25th draft - fix  alignment issue
     -   May 16, 2013  
   * -   2.4  
     -   1045 PCI OpROM Device ListChanges  to section 14.2
     -   June 28, 2013  
   * -   2.4  
     -   1044Corrections to Mantis 1015,  Interruptible driver diagnostics
     -   May 16, 2013  
   * -   2.4  
     -   1037 Add 2.4 to the system table  version
     -   May 16, 2013  
   * -   2.4
     -   1036Comments on April 25 Draft
     -   May 16, 2013
   * -   2.4  
     -   1033 HiiConfigAccess->ExtractConfig  StatusCodes Errata
     -   May 16, 2013  
   * -   2.4    
     -   1032  HiiConfigRouting->ExtractConfig  StatusCodes Errata
     -   May 16, 2013    
   * -   2.4
     -   1031 NVMe subtypeConflict errata
     -   April 25, 2013
   * -   2.4    
     -   1029 Method for delivery ofCapsule  on disk; Method for  reportingCapsule processing status
     -   April 25, 2013    
   * -   2.4  
     -   1026 (supersedes 993) Update to the  AArch64 proposedBindingChange
     -   April 25, 2013  
   * -   2.4  
     -   1024Clarification to the NVMe  Device Path text descriptions
     -   April 25, 2013  
   * -   2.4    
     -   1023 Definition ofCapsule format to  deliver update image to firmware  management protocol
     -   April 25, 2013    
   * -   2.4      
     -   1022 adapter information protocol  for NIC iSCSI and  FCoEBootCapabilities  andCurrentBooot Mode.
     -   April 25, 2013      
   * -   2.4  
     -   1017 AIP Instance - FCOE SAN MAC  Address
     -   April 25, 2013  
   * -   2.4
     -   1016 AIP Instance - Image Update
     -   April 25, 2013
   * -   2.4  
     -   1015 Interruptible driver  diagnostics
     -   April 25, 2013  
   * -   2.4    
     -   1009 Enable hashes ofCertificates  toBe used for revocation, and  timestamp support
     -   April 25, 2013    
   * -   2.4  
     -   1008 New Random Number Generator /  Entropy Protocol
     -   April 25, 2013  
   * -   2.4    
     -   1007Create a new Security  Technologies section to  avoidBlurring with SecureBoot
     -   April 25, 2013    
   * -   2.4
     -   1002 Timestamp Protocol
     -   April 25, 2013
   * -   2.3.1D  
     -   996 UEFI 2.0 version number still  in the 2.3.1C spec
     -   April 3, 2013  
   * -   2.3.1D
     -   995CSA linkChange
     -   April 3, 2013
   * -   2.3.1D
     -   994 Spec typos
     -   April 3, 2013
   * -   2.3.1D    
     -   990 EFI_ATA_PASS_THRU need  oneClarification if it supports  ATAPI device
     -   April 3, 2013    
   * -   2.3.1D  
     -   989Clarify hot-remove  responsibility of aBus Driver
     -   April 3, 2013  
   * -   2.3.1D      
     -   988  EFI_BLOCK_IO2_PROTOCOLBlocksChild  from stopping while doing  non-blocking I/O
     -   April 3, 2013      
   * -   2.3.1D    
     -   987 EFI_BLOCK_IO2_PROTOCOL has  aCopy pasteBug describing the Token  Parameter
     -   April 3, 2013    
   * -   2.3.1D
     -   980 Errata on SNP Media detect
     -   April 3, 2013
   * -   2.3.1D  
     -   978 Error Retun IndicatesCapsule  requiresBoot Services
     -   April 3, 2013  
   * -   2.3.1D
     -   977 missing statement
     -   April 3, 2013
   * -   2.3.1D  
     -   976BrowserCallback text update to  description
     -   April 3, 2013  
   * -   2.3.1D  
     -   975 UNDI errata to add missing  memory type definitions
     -   April 3, 2013  
   * -   2.3.1D  
     -   974 UNDI IncorrectCPB function  names ECR
     -   April 3, 2013  
   * -   2.3.1D
     -   973 UNDI Mem_Map()Clarification
     -   April 3, 2013
   * -   2.3.1D
     -   972 ISCSI DHCP6Boot
     -   April 3, 2013
   * -   2.3.1D
     -   971 typo
     -   April 3, 2013
   * -   2.3.1D  
     -   970 Typo section 28.3.8.3.41  EFI_IFR_MODAL_TAG
     -   April 3, 2013  
   * -   2.3.1D
     -   965 File IO Async extenstion
     -   April 3, 2013
   * -   2.3.1D  
     -   962 Remove 2.3 table revision  number
     -   April 3, 2013  
   * -   2.3.1D
     -   960 Typo in netboot6 description
     -   April 3, 2013
   * -   2.3.1D    
     -   959 InstallAcpiTable() does not say  what to do when an attempt is made  to install a duplicate table
     -   April 3, 2013    
   * -   2.3.1D
     -   955Clearing The Platform Key Errata
     -   April 3, 2013
   * -   2.3.1D
     -   954 LoadImage Errata
     -   April 3, 2013
   * -   2.3.1D  
     -   953 Need text definitions for  Device Path Media Type Subtype 6/7
     -   April 3, 2013  
   * -   2.3.1D    
     -   952Clarification of requirements to  update timestamp associated with  authenticated variable
     -   April 3, 2013    
   * -   2.3.1D    
     -   950 IndeterminateBehavior for  attribute modifications mayCause  security issues
     -   April 3, 2013    
   * -   2.3.1D    
     -   949 PCI IO.GetBarAttributes needs  adjustment - - Address Space  Granularity field
     -   April 3, 2013    
   * -   2.3.1D
     -   944 Errata - Replace RFC reference
     -   April 3, 2013
   * -   2.3.1D  
     -   943 Errata - Proposed updates to  required interfaces inChapter 2.6
     -   April 3, 2013  
   * -   2.3.1D  
     -   942 ExportConfig() description does  not make sense
     -   April 3, 2013  
   * -   2.3.1D  
     -   941 Add OEM StatusCode ranges to  EFI StatusCode Ranges Table
     -   April 3, 2013  
   * -   2.3.1D      
     -   938  InstallMultipleProtocolInterface()  is missing StatusCode Returned  values
     -   April 3, 2013      
   * -   2.3.1D  
     -   935ClarifyChaining requirements  with regards to the Platform Key
     -   April 3, 2013  
   * -   2.3.1D
     -   934 Missing Figures and typos
     -   April 3, 2013
   * -   2.3.1D  
     -   930Clarify usage of EFI Variable  Varstores in HII
     -   April 3, 2013  
   * -   2.3.1D
     -   928Best Matching Language algorithm
     -   April 3, 2013
   * -   2.3.1D  
     -   926 UEFI Image  VerificationClarification
     -   April 3, 2013  
   * -   2.3.1D    
     -   924 New ErrorCode to handle  reporting of IPV4 duplicate address  detection
     -   April 3, 2013    
   * -   2.3.1D  
     -   1021 ATA_PASS_THRU on ATAPI device  handle.
     -   April 3, 2013  
   * -   2.3.1D  
     -   1020Clarify HII variable store  definitions.
     -   April 3, 2013  
   * -   2.3.1D  
     -   1019 Alignment  RequirementsClarification
     -   April 3, 2013  
   * -   2.3.1D
     -   1018 HII Font Errata
     -   April 3, 2013
   * -   2.3.1D
     -   1013 HII Errata
     -   April 3, 2013
   * -   2.3.1D
     -   1012 Touchup to text of GPT
     -   April 3, 2013
   * -   2.3.1D  
     -   1011 Typo regarding Debug Port in  UEFI Spec
     -   April 3, 2013  
   * -   2.3.1D
     -   1003 Missing "(" in section 11.7
     -   April 3, 2013
   * -   2.3.1D  
     -   1000Clarification to the IFR_REF4  opcode
     -   April 3, 2013  
   * -   2.3.1C  
     -   921 Length of IPv6 Device Path is  incorrect
     -   June 13, 2012  
   * -   2.3.1C  
     -   917 UNDI drive does not need toBe  initialized as runtime driver
     -   June 13, 2012  
   * -   2.3.1C    
     -   915 For x64,Change Floating Point  DefaultConfiguration to  Double-Extended Precision
     -   June 13, 2012    
   * -   2.3.1C  
     -   914 Error Descriptor Reset  FlagClarification
     -   June 13, 2012  
   * -   2.3.1C  
     -   913 Enum definition does not match  what ourCurrentCompilers implement.
     -   June 13, 2012  
   * -   2.3.1C
     -   912 UEFI 2.3.1 Type
     -   June 13, 2012
   * -   2.3.1C  
     -   909 Update to returnCodes for  AllocatePool / AllocatePages
     -   June 13, 2012  
   * -   2.3.1C
     -   907 iSCSI Device Path error
     -   June 13, 2012
   * -   2.3.1C  
     -   882 Indications Variable - OS/FW  feature &CapabilityCommunication
     -   June 13, 2012  
   * -   2.3.1C  
     -   882 Indications Variable - OS/FW  feature &CapabilityCommunication
     -   June 13, 2012  
   * -   2.3.1C  
     -   874 Provide a mechanism for  providing keys in setup mode
     -   June 13, 2012  
   * -   2.3.1C  
     -   831 PXEBootCSA Type  definitionCleanup
     -   June 13, 2012  
   * -   2.3.1B  
     -   896 StartImage andConnectController  returnCodes
     -   April 10, 2012  
   * -   2.3.1B  
     -   893 SMMCommunication ACPI Table  Update
     -   April 10, 2012  
   * -   2.3.1B  
     -   891Component Name Protocol  References
     -   April 10, 2012  
   * -   2.3.1B  
     -   890 DriveConfiguration Protocol  Phantom.
     -   April 10, 2012  
   * -   2.3.1B
     -   888 typo in EFI_USB_HC Protocol
     -   April 10, 2012
   * -   2.3.1B  
     -   887 union is declared twice in same  section
     -   April 10, 2012  
   * -   2.3.1B  
     -   885 Errata in the GPT Table  structureComment
     -   April 10, 2012  
   * -   2.3.1B  
     -   884 EFI_BOOT_KEY_DATA relies on  implementation-definedBehavior
     -   April 10, 2012  
   * -   2.3.1B  
     -   881 netboot6 - multicast versus  unicast
     -   April 10, 2012  
   * -   2.3.1B
     -   880 netboot6Clarification/errata
     -   April 10, 2012
   * -   2.3.1B  
     -   879 Reference to unsupported  specification in SCSIChapter (14.1)
     -   April 10, 2012  
   * -   2.3.1B    
     -   878 Updated HII "Selected  Form"Behaviors to Reflect  NewCallback Results
     -   April 10, 2012    
   * -   2.3.1B    
     -   877 TableChecksum updateBy the  A  CPI_TABLE_PROTOCOL.InstallAcpiTable
     -   April 10, 2012    
   * -   2.3.1B    
     -   876 ToClarify EDID_OVERRIDE  attribute definitions and expected  operations
     -   April 10, 2012    
   * -   2.3.1B    
     -   873 Section 9.3.7 incorrectly  assumes that all uses ofBBS device  paths are non-UEFI
     -   April 10, 2012    
   * -   2.3.1B    
     -   872Change to  SIMPLE_TEXT_INPUT_EX_PROTOCOL.Re  gisterKeyNotify/UnregisterKeyNotify
     -   April 10, 2012    
   * -   2.3.1B  
     -   871 Typo in  InstallMultipleProtocolInterfaces
     -   April 10, 2012  
   * -   2.3.1B      
     -   870Clarify FrameBufferSize  definition under  EFI_GRAPHICS_OUTPUT_PROTOCOL_MODE  struct
     -   April 10, 2012      
   * -   2.3.1B  
     -   869 Reference to FIPS 180 inChapter  27.3 is obsolete and incorrect
     -   April 10, 2012  
   * -   2.3.1B  
     -   867Clarify requirment for use of  EFI_HASH_SERVICE_BINDING_PROTOCOL
     -   April 10, 2012  
   * -   2.3.1B  
     -   866 PK, KEK, db, dbx  relationsClarification
     -   April 10, 2012  
   * -   2.3.1B  
     -   865 Modify Protective  MBRBootIndicator definition
     -   April 10, 2012  
   * -   2.3.1B  
     -   864 Typo in Question-Level  Validation section
     -   April 10, 2012  
   * -   2.3.1B  
     -   863 Attributes of the Globally  Defined Variables
     -   April 10, 2012  
   * -   2.3.1B
     -   862 User identity typo
     -   April 10, 2012
   * -   2.3.1B  
     -   861 Globally Defined Variables  Errata
     -   April 10, 2012  
   * -   2.3.1B  
     -   858 Superfluous and incorrect image  hash description
     -   April 10, 2012  
   * -   2.3.1B
     -   857 Absolute pointer typo
     -   April 10, 2012
   * -   2.3.1B  
     -   855Clarification of UEFI driver  signing/Code definitions
     -   April 10, 2012  
   * -   2.3.1B    
     -   853 The EFI_HASH_PROTOCOL.Hash()  description needsClarification on  padding responsibilities
     -   April 10, 2012    
   * -   2.3.1B  
     -   852 Various EFI_IFR_REFRESH_ID  errata.
     -   April 10, 2012  
   * -   2.3.1B    
     -   851 For EFI_IFR_REFRESH  opcode,Clarify RefreshInterval = 0  means no auto-refresh.
     -   April 10, 2012    
   * -   2.3.1B    
     -   850Clarification of responsibility  for array allocation in  EFI_HASH_PROTOCOL
     -   April 10, 2012    
   * -   2.3.1B    
     -   849 IFR EFI_IFR_MODAL_TAG_OP is  also valid under  EFI_IFR_FORM_MAP_OP
     -   April 10, 2012    
   * -   2.3.1B  
     -   848Clarification of semantics of  SecureBoot variable
     -   April 10, 2012  
   * -   2.3.1B    
     -   847 When enrolling a PK, the  platform shall not require a reboot  to leave SetupMode
     -   April 10, 2012    
   * -   2.3.1B  
     -   845 EFI_SCSI_PASS_THRU_PROTOCOL  replacement
     -   April 10, 2012  
   * -   2.3.1B  
     -   842 Text to explain how the UEFI  revision is referred
     -   April 10, 2012  
   * -   2.3.1B    
     -   836 StructureComment for  EFI_IFR_TYPE_VALUE references  unknown value type.
     -   April 10, 2012    
   * -   2.3.1B
     -   828 Network Driver Options
     -   April 10, 2012
   * -   2.3.1B
     -   826Comments against Mantis 790
     -   April 10, 2012
   * -   2.3.1B
     -   825 DMTF SMCLP errata
     -   April 10, 2012
   * -   2.3.1B  
     -   819 Mantis 715 was not fully  implemented
     -   April 10, 2012  
   * -   2.3.1B
     -   812 Errata – DUID-UUID usage
     -   April 10, 2012
   * -   2.3.1B  
     -   809 Errata – Messaging Device  PathClarification
     -   April 10, 2012  
   * -   2.3.1B
     -   808 Errata –Boot File URL
     -   April 10, 2012
   * -   2.3.1B  
     -   807 Give specific TPL rules to  Stall()Boot services
     -   April 10, 2012  
   * -   2.3.1B
     -   771 SHA1 and MD5 references
     -   April 10, 2012
   * -   2.3.1A        
     -   MinorCorrections in toes to tickets  772, 785, 794, 804, also  formattingCorrection for  \_WIN_CERTIFICATE_UEFI_GUID  typedef’s parameters
     -   September 7, 2011        
   * -   2.3.1A  
     -   820 Driver Health Needs to have  Mantis 0000169 implemented
     -   August 17, 2011  
   * -   2.3.1A  
     -   819 ECR715 was not fully  implemented
     -   August 17, 2011  
   * -   2.3.1A    
     -   806 Text update to Driver Health  Description -Clarify role of user  interaction
     -   August 17, 2011    
   * -   2.3.1A  
     -   805Correct Wrong Palette  Information in 28.3.7.2.3 example
     -   August 17, 2011  
   * -   2.3.1A    
     -   804ClarifyContraints and  alternatives when enrolling PK,  KeK, db or dbx keys
     -   August 17, 2011    
   * -   2.3.1A  
     -   803 Fix AcpiExp device node text  description.
     -   August 17, 2011  
   * -   2.3.1A  
     -   801ClarifyIFR Opcode Summary and  Description #4
     -   August 17, 2011  
   * -   2.3.1A  
     -   800Clarify IFR Opcode Summary and  Description #3
     -   August 17, 2011  
   * -   2.3.1A  
     -   797Clarify IFR Opcode Summary and  Description #2
     -   August 17, 2011  
   * -   2.3.1A  
     -   796Clarify IFR Opcode Summary and  Description #1
     -   August 17, 2011  
   * -   2.3.1A
     -   795 Typo in ReadKeyStrokeEx()
     -   August 17, 2011
   * -   2.3.1A  
     -   794 Incomplete text  describingClearing of Platform Key
     -   August 17, 2011  
   * -   2.3.1A  
     -   793 Inconsistent wording about  RemainingDevicePath
     -   August 17, 2011  
   * -   2.3.1A  
     -   790 Add warning to ReadKeyStrokeEx  for partial key press
     -   August 17, 2011  
   * -   2.3.1A
     -   789Clarify HII opcode definition
     -   August 17, 2011
   * -   2.3.1A      
     -   788 SasEx entry in Table 86-Device  Node TableContains optional  Reserved entry that does not exist  in device path
     -   August 17, 2011      
   * -   2.3.1A  
     -   786 PCI I/O Dual AddressCycle  attributeClarification
     -   August 17, 2011  
   * -   2.3.1A    
     -   785 Allowing more general use of  UEFI 2.3.1 Variable time-based  authentication
     -   August 17, 2011    
   * -   2.3.1A  
     -   780 Errata in returnCode  descriptions
     -   August 17, 2011  
   * -   2.3.1A      
     -   778  EFI_HI  I_CONFIG_ACCESS_PROTOCOL.CallBack()  Errata
     -   August 17, 2011      
   * -   2.3.1A  
     -   777 Specified signature sizes  incorrect in Section 27.6.1
     -   August 17, 2011  
   * -   2.3.1A    
     -   776 Clarifycomputation of  EFI_VARIABLE\_ AUTHENTICATION_2 hash value
     -   August 17, 2011    
   * -   2.3.1A  
     -   774 Define  EFI_BLOCK_IO_PROTOCOL_REVISION3
     -   August 17, 2011  
   * -   2.3.1A  
     -   773Clarify the value for opcode  EFI_IFR_REFRESH_ID_OP
     -   August 17, 2011  
   * -   2.3.1A    
     -   772 Definition of  EFI_IMAGE_SECURITY_DATABAE_GUID  incorrect
     -   August 17, 2011    
   * -   2.3.1A  
     -   770 Remove references to UEFI 2.1  spec
     -   August 17, 2011  
   * -   2.3.1A    
     -   767 The ReadBlocks function  forBlockIO andBlockIO2 need  synchronization
     -   August 17, 2011    
   * -   2.3.1A    
     -   212 (revisit) final sentence  section 28.2.15 missing final  words.
     -   April 21, 2011    
   * -   2.3.1    
     -   765 ECR to limit the hash and  encryption algorithms used with  PKCSCertificates
     -   April 5, 2011    
   * -   2.3.1  
     -   762 DevicePath in the Image  Execution Information Table.
     -   April 5, 2011  
   * -   2.3.1  
     -   761 Table 195. Information for  Types of Storage
     -   April 5, 2011  
   * -   2.3.1  
     -   760 SuggestedChanges to 2.3.1 final  draft spec
     -   April 5, 2011  
   * -   2.3.1  
     -   759 UEFI Errata - wincerts for rest  of hash algorithms
     -   April 5, 2011  
   * -   2.3.1  
     -   755 Errata in Legacy MBR table and  Legacy MBR GUID
     -   April 5, 2011  
   * -   2.3.1
     -   754 USB timeout parameter mismatch.
     -   April 5, 2011
   * -   2.3.1  
     -   751 Fix USB HC2 erroneous  references to IsSlowDevice
     -   March 11, 2011  
   * -   2.3.1    
     -   750 Fix section 27.2.5 "related  definitions" re: RSA public key  exponent
     -   March 11, 2011    
   * -   2.3.1  
     -   749 Fix Table 10 (Global Variables)  WithCorrect Attributes
     -   March 11, 2011  
   * -   2.3.1  
     -   748Clarify Standard GUID Text  Representation
     -   March 11, 2011  
   * -   2.3.1  
     -   744 ProcessorContext information  structure definition notClear
     -   March 11, 2011  
   * -   2.3.1  
     -   741 Errata:Corrected text for  section 7.2.1.4 step 7
     -   March 11, 2011  
   * -   2.3.1  
     -   740 Errata: signatureheadersize  inconsistencyCorrections
     -   April 6, 2011  
   * -   2.3.1    
     -   736 Insert SMMCommunication ACPI  Table and related data structures  to the UEFI Specification
     -   April 5, 2011    
   * -   2.3.1  
     -   735Clarification on Tape Header  Format
     -   March 11, 2011  
   * -   2.3.1
     -   734 SecureBoot variable
     -   April 5, 2011
   * -   2.3.1  
     -   733 Errata: 27.6.1  signatureheadersize definition
     -   March 11, 2011  
   * -   2.3.1  
     -   732 Amendment to Mantis 711:  section 7.2.1.6
     -   March 11, 2011  
   * -   2.3.1  
     -   729 Errata:Clarification of  Microsoft references in appendix Q
     -   March 11, 2011  
   * -   2.3.1
     -   728 Netboot 6 errata - DUID-UUID
     -   March 11, 2011
   * -   2.3.1  
     -   727 Errata on returnCode for User  Info Identity policy record
     -   March 11, 2011  
   * -   2.3.1    
     -   726 Errata/clean-up of  EFI_DHCP4_TRANSMIT_RECEIVE\_ TOKEN  definition
     -   March 11, 2011    
   * -   2.3.1
     -   724 SetVariable Update 2
     -   March 11, 2011
   * -   2.3.1    
     -   723 User Identification (UID)  Errata – EFI User Manager Notify &  EnrollClarification
     -   April 5, 2011    
   * -   2.3.1    
     -   722 User Identification (UID)  Errata –Credential Provider  EnrollClarification
     -   April 5, 2011    
   * -   2.3.1  
     -   721 User Identification (UID)  Errata – SetInfoClarification
     -   March 11, 2011  
   * -   2.3.1    
     -   720 User Identification (UID)  Errata –Credential Provider  EnrollClarification
     -   March 11, 2011    
   * -   2.3.1        
     -   716  EFI_EXT_SCSI_PASS_THRU\_ PROTOCOL.GetNextTarget()  IN OUT parameter Target input value  shallBe 0xFFs
     -   March 11, 2011        
   * -   2.3.1  
     -   715CPER Record and section  fieldClarification
     -   March 11, 2011  
   * -   2.3.1  
     -   713 Remove the errata revision from  the EFI_IFR_VERSION format.
     -   March 11, 2011  
   * -   2.3.1
     -   711 SetVariable Update
     -   March 11, 2011
   * -   2.3.1  
     -   709 NewCallback() Action Requests  Related To Individual Forms.
     -   Feb. 3, 2011  
   * -   2.3.1
     -   708 Errata (non-blockingBLOCK IO)
     -   April 5, 2011
   * -   2.3.1  
     -   707 Errata revision in the  EFI_IFR_VERSION format
     -   Feb. 3, 2011  
   * -   2.3.1  
     -   705 REPC signature definition  stillConfusing
     -   Feb. 3, 2011  
   * -   2.3.1
     -   704 Unload() definition is wrong
     -   Feb. 3, 2011
   * -   2.3.1  
     -   702Clarifications on Variable  Storage for Questions
     -   Feb. 3, 2011  
   * -   2.3.1    
     -   696 Update System Table with this  new #define for  EFI_SYSTEM_TABLE_REVISION
     -   Feb. 3, 2011    
   * -   2.3.1
     -   695 Add Port Ownership probing
     -   Feb. 3, 2011
   * -   2.3.1  
     -   687 Update System Table with this  new #define for 2.3.1
     -   Jan. 17, 2011  
   * -   2.3.1  
     -   686 HII -Clarify FormsBrowser  'standard' user interfactions.
     -   Feb. 3, 2011  
   * -   2.3.1    
     -   685 HII - New op-code to enable  event initiated refresh  ofBrowserContext data
     -   Feb. 3, 2011    
   * -   2.3.1
     -   682 [UCST] Modal Form
     -   Feb. 3, 2011
   * -   2.3.1
     -   681 Typo: Pg. 56
     -   Jan. 17, 2011
   * -   2.3.1
     -   680 Netboot6 handleClarification
     -   Jan. 17, 2011
   * -   2.3.1  
     -   679 UEFI Authenticated Variable &  Signature Database Updates
     -   Jan. 17, 2011  
   * -   2.3.1  
     -   678 Section 27.6.2: Imagehash  reference needs toBe removed
     -   Jan. 17, 2011  
   * -   2.3.1  
     -   677 Section 27.2.5 & 27.6.1: Typo  in X509 Signature Type
     -   Jan. 17, 2011  
   * -   2.3.1  
     -   674 Section 3.2: Missing variable  type for SetupMode variable
     -   Jan. 17, 2011  
   * -   2.3.1  
     -   671 Errata: USB device path example  is incorrect
     -   Jan. 17, 2011  
   * -   2.3.1  
     -   668 LUN implementations are  notConsistent
     -   Feb. 3, 2011  
   * -   2.3.1
     -   661 USB 3.0 Updates
     -   Oct. 29, 2010
   * -   2.3.1    
     -   645 Non-blocking interface forBLOCK  oriented devices (BLOCK_IO_EX  transition toBLOCK_IO_2)
     -   Oct. 29, 2010    
   * -   2.3.1
     -   634 FormsBrowser DefaultBehavior
     -   Jan. 17, 2011
   * -   2.3.1
     -   634 FormsBrowser DefaultBehavior
     -   Oct. 29, 2010
   * -   2.3.1  
     -   616 Security ProtocolCommand to  support encrypted HDD
     -   Jan. 17, 2011  
   * -   2.3.1  
     -   616 Security ProtocolCommand to  support encrypted HDD
     -   Oct. 29, 2010  
   * -   2.3.1  
     -   612 UEFI system Partition FAT32  data Region Alignment
     -   Oct. 29, 2010  
   * -   2.3.1
     -   484 Key Management Service Protocol
     -   Oct. 28, 2010
   * -   2.3.1  
     -   484 Key Management Service (KMS)  Protocol
     -   Oct. 29, 2010  
   * -   2.3.1  
     -   478 (REVISIT) Update to ALTCFG  references
     -   March 11, 2011  
   * -   2.3 D  
     -   667Clarification to the  UEFIConfiguration Table definition
     -   Oct. 28, 2010  
   * -   2.3 D  
     -   664 Appendix update for IPV6  networkBoot
     -   Oct. 28, 2010  
   * -   2.3 D    
     -   663 Update ARM PlatformBinding to  allow OS loader to assume unaligned  access support is enabled
     -   Nov. 10, 2010    
   * -   2.3 D
     -   662 ARM ABI errata
     -   Oct. 28, 2010
   * -   2.3 D  
     -   659Clarify section length  definition in the error record
     -   Oct. 28, 2010  
   * -   2.3 D  
     -   653 Errata to the Appendix N  (Common Platform Error Record)
     -   Oct. 28, 2010  
   * -   2.3 D  
     -   652Clarification to the TimeZone  value usage
     -   Oct. 28, 2010  
   * -   2.3 D  
     -   651 update to IPSec for tunnel mode  support
     -   Oct. 28, 2010  
   * -   2.3 D
     -   650 networking support errata
     -   Oct. 28, 2010
   * -   2.3 D  
     -   638 Add facility for dynamic IFR  dynamicCross-references
     -   Oct. 28, 2010  
   * -   2.3 D
     -   538 IPV6 PXE
     -   Oct. 28, 2010
   * -   2.3C
     -   640 String ReferenceCleanup
     -   July 14, 2010
   * -   2.3C  
     -   639Callback() does not describe  FORM_OPEN/FORM_CLOSEBehavior
     -   July 14, 2010  
   * -   2.3C  
     -   637Clarification for Date/Time  Question usage in IFR expressions.
     -   July 14, 2010  
   * -   2.3C    
     -   636 Mistaken Reference to "Date"  inside ofBoolean question  description
     -   July 14, 2010    
   * -   2.3C  
     -   635 Missing GUID label forConfig  Access protocol
     -   July 14, 2010  
   * -   2.3C  
     -   633 Explicitly Specify ACPI Table  Signature Format
     -   July 14, 2010  
   * -   2.3C    
     -   632ClarifyBlock IO ReadBlocks and  WriteBlocks functions handling of  media stateChange events
     -   July 14, 2010    
   * -   2.3C    
     -   625 Minor typo in  surrogateCharacter description  section
     -   July 14, 2010    
   * -   2.3C
     -   622 Identify() function errata
     -   July 14, 2010
   * -   2.3C      
     -   621 Typos in an  EFI_HII_CONFIG_ACCESS\_ PROTOCOL.Callback()  member
     -   July 14, 2010      
   * -   2.3C  
     -   620Carification of need for Path  MTU support for IPV4 and IPV6
     -   July 14, 2010  
   * -   2.3C
     -   613 PAUSE Key
     -   July 14, 2010
   * -   2.3C      
     -   611 LanguageCorrection requested  for InstallProtocolInterface() and  InstallConfigurationTable(), Ref#  583
     -   July 14, 2010      
   * -   2.3C
     -   610 RSA data structureClarification
     -   July 14, 2010
   * -   2.3C
     -   609 StartImage returnCode update
     -   July 14, 2010
   * -   2.3C  
     -   583 How do we know an EFI_HANDLE is  Valid/Invalid
     -   July 14, 2010  
   * -   2.3C  
     -   508 Update networking references,  incl ipv6
     -   July 14, 2010  
   * -   2.3B
     -   608 more media detectClean-up
     -   Feb. 24, 2010
   * -   2.3B
     -   605Clarify user identity Find API
     -   Feb. 24, 2010
   * -   2.3B  
     -   601 UNDI update as part of media  detectChanges
     -   Feb. 24, 2010  
   * -   2.3B  
     -   600 Update  toConfigAccess/ConfigRouting
     -   Feb. 24, 2010  
   * -   2.3B
     -   598 ARP is only an IPV4Concept.
     -   Feb. 24, 2010
   * -   2.3B
     -   590 Media detectClean-up
     -   Feb. 24, 2010
   * -   2.3B  
     -   589 Device path representation of  IPv4/v6 text
     -   Feb. 24, 2010  
   * -   2.3B  
     -   588 UEFI User Identity -  ReturnCodes
     -   Feb. 24, 2010  
   * -   2.3B  
     -   587 UEFI User Identity -  NamingConsistency
     -   Feb. 24, 2010  
   * -   2.3B    
     -   586Clarification of PXE2.1  specification for IPV4  interoperability issues
     -   Feb. 24, 2010    
   * -   2.3B
     -   585 Errata to EFI_IFR_SET op-code
     -   Feb. 24, 2010
   * -   2.3B  
     -   584 EFI_PXE_BASE_CODE_DHCPV6_PACKET  missing for pxeBc protocol
     -   Feb. 24, 2010  
   * -   2.3B  
     -   583 How do we know an EFI_HANDLE is  Valid/Invalid
     -   Feb. 24, 2010  
   * -   2.3B    
     -   580  ACPI_SUPPORT_PROTOCOLClarifications  related to FADT and the DSDT/FACS
     -   Dec. 15, 2009    
   * -   2.3B  
     -   578 ATA Passthrough updates /  questions
     -   Dec. 15, 2009  
   * -   2.3B  
     -   577Clarifications on the user  identity protocol
     -   Dec. 15, 2009  
   * -   2.3B  
     -   576Clarifications in the Routing  Protocol
     -   Dec. 15, 2009  
   * -   2.3B  
     -   575 Machine hand-off/MP state  modification
     -   Feb. 24, 2010  
   * -   2.3B  
     -   574 Add an "OPTIONAL" tag to a  parameter in NewPackageList
     -   Dec. 15, 2009  
   * -   2.3B  
     -   573 EFI_DESCRIPTION_STRING and  EFI_DESCRIPTION_BUNDLE adjustments
     -   Feb. 24, 2010  
   * -   2.3B  
     -   572 EFI_IFR_SECURITY shouldBe  EFI_IFR_SECURITY_OP in Table 194
     -   Dec. 15, 2009  
   * -   2.3B
     -   568 ATA_STATUS_BLOCK name errata
     -   Dec. 15, 2009
   * -   2.3B  
     -   567 Various miscellaneous  typos/updates
     -   Feb. 24, 2010  
   * -   2.3B  
     -   566 Minor update to HII->NewString  function description
     -   Dec. 15, 2009  
   * -   2.3B  
     -   560Correct erroneous example in  ExtractConfig()
     -   Dec. 15, 2009  
   * -   2.3B  
     -   559 Extraneous "default" tag in  EFI_IFR_SECUITY grammar
     -   Dec. 15, 2009  
   * -   2.3B  
     -   558Clarify VLANConfig publication  requirements
     -   Dec. 15, 2009  
   * -   2.3B  
     -   557Corrected Image Execution  Information omission & ambiguity
     -   Dec. 15, 2009  
   * -   2.3B
     -   556 additional IPSec errata/issues
     -   Dec. 15, 2009
   * -   2.3B
     -   549Binary prefixChange
     -   Dec. 15, 2009
   * -   2.3B
     -   547Clean-Up In HII Sections
     -   Dec. 15, 2009
   * -   2.3B
     -   546 typo in GOP definiton
     -   Dec. 15, 2009
   * -   2.3B    
     -   545 Action parameter of the  EFI_HI  I_CONFIG_ACCESS_PROTOCOL.CallBack()
     -   Dec. 15, 2009    
   * -   2.3B
     -   542 Device Path DescriptionChanges
     -   Dec. 15, 2009
   * -   2.3B
     -   540 Register name usage
     -   Dec. 15, 2009
   * -   2.3B
     -   539CHAP node fix for iSCSI
     -   Dec. 15, 2009
   * -   2.3B  
     -   537 Add missing ACPI ADR Device  Path Representation
     -   Dec. 15, 2009  
   * -   2.3B
     -   536 IPSec errata
     -   Dec. 15, 2009
   * -   2.3B  
     -   534 Size of Partition Entry  restriction
     -   Dec. 15, 2009  
   * -   2.3B
     -   533 GPT editorialCleanup
     -   Dec. 15, 2009
   * -   2.3B  
     -   532 "LegacyBIOSBootable" GPT  attribute
     -   Dec. 15, 2009  
   * -   2.3B
     -   531Clarify HII Variable Storage
     -   Dec. 15, 2009
   * -   2.3B  
     -   519 AddConsole table (chapt 11) for  EFI_SIMPLE_TEXST_INPUT_EX_PROTOCOL
     -   Dec. 15, 2009  
   * -   2.3B  
     -   518 Typos in the UEFI2.3  specification
     -   Feb. 24, 2010  
   * -   2.3B  
     -   515 Authenticated  VariablesClarification
     -   Feb. 24, 2010  
   * -   2.3B  
     -   514 HIIConfiguration String  SyntaxClarification
     -   Feb. 24, 2010  
   * -   2.3B  
     -   507Clarify ACPI Protocol’s position  onChecksums
     -   Dec. 15, 2009  
   * -   2.3B  
     -   479 TPM guideline added to section  2.6.2
     -   Dec. 15, 2009  
   * -   2.3B  
     -   476 Text adjustment toConfigAccess  &ConfigRouting
     -   Dec. 15, 2009  
   * -   2.3B
     -   460 Section 2.6 languageChange
     -   Dec. 15, 2009
   * -   2.3B  
     -   454 Dynamic support of media  dectection - network stack
     -   Dec. 15, 2009  
   * -   2.3B  
     -   431 UEFI 2.3 Feb Draft: Section  30.4
     -   Feb. 24, 2010  
   * -   2.3B  
     -   301 Errata to the Authentication  Protocol
     -   Dec. 15, 2009  
   * -   2.3B    
     -   215 previously added to Device  Driver (wrong), nowBusDriver  (correct)
     -   Dec. 15, 2009    
   * -   2.3A    
     -   522Bugs in  EFI_CERT_BLOCK_RSA_2048_SHA256,  ISCSI device path,CHAP device path
     -   Sept 15, 2009    
   * -   2.3A
     -   518 typos
     -   Sept 15, 2009
   * -   2.3A  
     -   517 IP stack related protocol  update
     -   Sept 15, 2009  
   * -   2.3A
     -   516 User Identity ProtocolBugs
     -   Sept 15, 2009
   * -   2.3A  
     -   513 add support for gateways in  ipv4 & ipv6 device path nodes
     -   Sept 15, 2009  
   * -   2.3A  
     -   506 TCP6/MTFTP6 StatusCode  Definition
     -   Sept 15, 2009  
   * -   2.3A
     -   505 TCP4/MTFTP4 statusCodes
     -   Sept 15, 2009
   * -   2.3A  
     -   490Correction 28.2.5.6, Table 185.  Information for Types of Storage
     -   Sept 15, 2009  
   * -   2.3A
     -   478 Update to ALTCFG references
     -   Sept 15, 2009
   * -   2.3A  
     -   477 Text adjustment  toConfigAccess/ConfigRouting
     -   Sept 15, 2009  
   * -   2.3  
     -   463 Update  EFI_IP6_PROTOCOL.Neighbors() API
     -   May 7, 2009  
   * -   2.3  
     -   462 ExitBootServices timers  deavtivation
     -   May 7, 2009  
   * -   2.3
     -   461IP4 Mode Data definition update
     -   May 7, 2009
   * -   2.3
     -   460Chapter 2.6 language update
     -   May 7, 2009
   * -   2.3  
     -   457Change KeyData.PackedValue to  0x40000200, page 63.
     -   May 7, 2009  
   * -   2.3  
     -   456 How to handle PXEBoot w/o NII  Section 21.3
     -   May 7, 2009  
   * -   2.3  
     -   454 Dynamic support of media  detection - network stack
     -   May 7, 2009  
   * -   2.3  
     -   453 Errata to support dynamic media  detection - UNDI
     -   May 7, 2009  
   * -   2.3  
     -   452 Support to dynamically detect  media errata - SNP
     -   May 7, 2009  
   * -   2.3  
     -   450 Missing opcode headers and  formatting, section 28.3.8.3.x.
     -   May 7, 2009  
   * -   2.3    
     -   449 Add missing EFI_IFR_GET,  EFI_IFR_SET and EFI_IFR_MAP to the  syntax.Section 28.2.5.7.
     -   May 7, 2009    
   * -   2.3      
     -   448 Section 28.2.5.4 Questions,  Syntax, Update question-option-tag;  Add EFI_IFR_READ and EFI_IFR_WRITE  in the question syntax.
     -   May 7, 2009      
   * -   2.3        
     -   447Section 28.2.5.11.2 Moving  Forms, Update line that starts with  EFI_IFR_FORM to: EFI_IFR_FORM or  EFI_IFR_FORM_MAP (and all  references in EFI_IFR_REF)
     -   May 7, 2009        
   * -   2.3            
     -   446 Section 28.2.5.2 Forms,  Syntax,Change 3rd line to:    form := EFI_IFR_FORM form-tag-list  \|    EFI_IFR_FORM_MAP form-tag-list
     -   May 7, 2009            
   * -   2.3  
     -   445 Table 194: EFI_IFR_FORM_MAP_OP,  2ndColumn shouldBe 0x5d (not 05xd)
     -   May 7, 2009  
   * -   2.3          
     -   444 Form Set Syntax: Section  28.2.5.1.1, section shouldBe  subheading, not heading level 5;  Section 28.2.5.1, Syntax, line 3,  text after := is not aligned with  other text on line 2, 4
     -   May 7, 2009          
   * -   2.3    
     -   443 Section 28.3.8.3.38,  EFI_IFR_MAP, Prototype, line 4,  outdent 2 spaces.
     -   May 7, 2009    
   * -   2.3    
     -   442 Section 28.3.8.3.64,  EFI_IFR_SET, Prototype, lines 3-8,  indentBy 2 spaces
     -   May 7, 2009    
   * -   2.3  
     -   440Change the defined type of  EFI_STATUs from INTN to UINTN
     -   May 7, 2009  
   * -   2.3      
     -   439 Incorrect definitions of  UEFI_CONFIG_LANG and  UEFI_CONFIG_LANG_2 in UEFI 2.3  Feb18 draft
     -   Feb 25, 2009      
   * -   2.3  
     -   438 UEFI 2.3 Feb 13 Draft:Chapter  28 Formatting Issues
     -   Feb 18, 2009  
   * -   2.3  
     -   437 Errata to 2.3 draft material  from UEFI Spec 2_3_Draft_Jan29
     -   Feb 18, 2009  
   * -   2.3  
     -   436 UEFI 2.3 split Figure 88 into 3  figures
     -   Feb. 12, 2009  
   * -   2.3  
     -   435 Partition  SignatureClarification
     -   Feb. 12, 2009  
   * -   2.3
     -   434 UEFI 2.3 Feb Draft: 28.3.8.3.58
     -   Feb. 12, 2009
   * -   2.3
     -   432 UEFI 2.3 Feb Draft: Appendix M.
     -   Feb. 12, 2009
   * -   2.3  
     -   431 UEFI 2.3 Feb Draft: Section  30.4
     -   Feb. 12, 2009  
   * -   2.3  
     -   418Change Appendix O from "UEFI  ACPI Table" to "UEFI ACPI Data
     -   Feb 18, 2009  
   * -   2.3  
     -   413Correct the definition of  UEFI_CONFIG_LANG
     -   Feb 18, 2009  
   * -   2.3
     -   410 UNDIBuffer usage
     -   Feb 18, 2009
   * -   2.3
     -   408 ARMBindingCorrections
     -   Feb. 12, 2009
   * -   2.3  
     -   406 Missing EFI System Table  Revision In UEFI 2.3 Draft
     -   Feb. 12, 2009  
   * -   2.3  
     -   395 New "Non-removable  MediaBootBehavior" section
     -   Feb. 12, 2009  
   * -   2.3  
     -   394 Omission in  EFI_USB2_HC_PROTOCOL
     -   Feb. 12, 2009  
   * -   2.3    
     -   388 Add HIICallback types  (FORM_OPEN, FORM_CLOSE) when a form  is opened orClosed.
     -   Feb. 12, 2009    
   * -   2.3  
     -   376 Add ARM processorBinding to  UEFI
     -   Jan. 12, 2009  
   * -   2.3  
     -   326 Add Firmware Management  Protocol
     -   Feb. 12, 2009  
   * -   2.2A    
     -   429  EFI_HASH_SERVICE_BINDING_PROTOCOL  GUID define misses \_GUID
     -   Feb. 12, 2009    
   * -   2.2A  
     -   404 RemoveConstraint form  EFI_TIME.YearComment
     -   Feb. 12, 2009  
   * -   2.2A
     -   400 FreePool() description error
     -   Feb. 12, 2009
   * -   2.2A  
     -   393 UEFI 2.1/2.2Boot  ManagerBehaviorClarification
     -   Feb. 12, 2009  
   * -   2.2A
     -   392 MBR errata in UEFI 2.2
     -   Feb. 12, 2009
   * -   2.2A  
     -   391 Polarity of INCONSISTENT_IF and  NO_SUBMIT_IF IFR opcodes wrong
     -   Feb. 12, 2009  
   * -   2.2A  
     -   390 UEFI 2.2 Miscellaneous  HII-related errata
     -   Feb. 12, 2009  
   * -   2.2A  
     -   389 UEFI 2.2 HII-Related Formatting  Issues
     -   Feb. 12, 2009  
   * -   2.2A
     -   387 UEFI 2.1/UEFI 2.2A (ch. 12)
     -   Feb. 12, 2009
   * -   2.2A  
     -   384 Fix HII package description  omission.
     -   Feb. 12, 2009  
   * -   2.2A  
     -   379 UEFI 2.1/UEFI 2.2 HII-Related  Errata
     -   Feb. 12, 2009  
   * -   2.2A  
     -   378 UEFI 2.1 & UEFI 2.2  HIICallbackClarifications
     -   Feb. 12, 2009  
   * -   2.2A
     -   377 MissingBLTBuffer figure.
     -   Feb. 12, 2009
   * -   2.2A  
     -   375 Extra periods errata in UEFI  2.2
     -   Feb. 12, 2009  
   * -   2.2A  
     -   374 UEFI 2.1 & UEFI 2.2A  (10.7-10.10)
     -   Feb. 12, 2009  
   * -   2.2A  
     -   373 UEFI 2.2,Chs. 9.5 & 9.6.2 &  9.6.3 (Device Path) Errata
     -   Feb. 12, 2009  
   * -   2.2A  
     -   372 UEFI 2.2 remove "Draft for  Review"
     -   Feb. 12, 2009  
   * -   2.2A  
     -   371 UEFI 2.1 & UEFI 2.2 Typos (ch.  10)
     -   Feb. 12, 2009  
   * -   2.2A  
     -   370 EFI_SYSTEM_TABLE Errata (UEFI  2.1/UEFI 2.2)
     -   Feb. 12, 2009  
   * -   2.2A  
     -   368 EFI_FONT_DISPLAY_INFO.FontInfo  description incorrect
     -   Feb. 12, 2009  
   * -   2.2A    
     -   366 UEFI 2.x: Erroneous references  to EFI_BOOT_SERVICES_TABLE,  EFI_RUNTIME_SERVICES_TABLE
     -   Feb. 12, 2009    
   * -   2.2A  
     -   364 UEFI 2.2 Typos & Formatting  Issues (ch. 9)
     -   Feb. 12, 2009  
   * -   2.2A
     -   362 UEFI 2.2 Typos (Next)
     -   Feb. 12, 2009
   * -   2.2A  
     -   361 UEFI 2.2 Typos & Formatting  Issues
     -   Feb. 12, 2009  
   * -   2.2A
     -   359 TPL Table
     -   Feb. 12, 2009
   * -   2.2A
     -   358 Missing signature for UEFI 2.2.
     -   Feb. 12, 2009
   * -   2.2  
     -   398 Update to M348 to fix small  typo
     -   Jan. 11, 2009  
   * -   2.2
     -   397 PCICopyMem() misspelling
     -   Jan. 11, 2009
   * -   2.2  
     -   394 Omission in  EFI_USB2_HC_PROTOCOL
     -   Jan. 11, 2009  
   * -   2.2    
     -   357Clarify  EFI_IFR_DISABLE_IFBehavior with  regard to dynamic values
     -   Jan. 11, 2009    
   * -   2.2  
     -   351 Fix an unaligned field in a  device path
     -   Jan. 11, 2009  
   * -   2.2
     -   350 EFI_HII_STRING_PROTOCOL Typos
     -   Jan. 11, 2009
   * -   2.2  
     -   348 EFI_IFR_RESET_BUTTON is  incorrectly listed as a question
     -   Jan. 11, 2009  
   * -   2.2    
     -   347 Replace first paragraph of the  "Description" section for the  ExitBootServices()
     -   Sept. 25, 2008    
   * -   2.2  
     -   346 Nest, Sections 10.11 & 10.12  Under 10.10
     -   Sept. 25, 2008  
   * -   2.2    
     -   344Correct missing statusCodes  returned section for Form() in  EFI_USER_CREDENTIAL_PROTOCOL.
     -   Sept. 25, 2008    
   * -   2.2    
     -   343Correct missing parameter for  User() function in  EFI_USER_CREDENTIAL_PROTOCOL
     -   Sept. 25, 2008    
   * -   2.2  
     -   340 UEFI 2.2 Editorial / Formatting  Issues
     -   Sept. 25, 2008  
   * -   2.2
     -   339 Update missing TPL restrictions
     -   Sept. 25, 2008
   * -   2.2      
     -   337 Replace the EFI_CRYPT_HANDLE  reference (in the IPSsec API)with a  self-contained, independent  definition.
     -   Sept. 25, 2008      
   * -   2.2
     -   335 User Authentication errata
     -   Sept. 25, 2008
   * -   2.2  
     -   334 Standardized "Unicode"  References
     -   Jan. 11, 2009  
   * -   2.2  
     -   333Correct the incorrect ';' at the  end of EFI_GUID #defines
     -   Sept. 25, 2008  
   * -   2.2    
     -   332Correct SendForm description  Type, PackageGuid and FormsetGuid  parameters
     -   Sept. 25, 2008    
   * -   2.2    
     -   331 Definition for  EFI_BROWSER_ACTION and the related  #defines were not present--Insert.
     -   Sept. 25, 2008    
   * -   2.2  
     -   330 EFI_IFR_REF:ChangeCross  reference to a question
     -   Sept. 25, 2008  
   * -   2.2    
     -   327Clarify the support in DHCP4  protocol for "Inform" (DHCPINFORM)  messages.
     -   Sept. 25, 2008    
   * -   2.2
     -   325 MinorCorrection 28.3.8.3.20
     -   July 25, 2008
   * -   2.2
     -   324 ATA Pass-Thru ECR Update
     -   July 25, 2008
   * -   2.2  
     -   323 VLAN modificationBecause of  IPV6
     -   July 25, 2008  
   * -   2.2  
     -   322Chapter 2 updates for IP6 net  stack
     -   July 25, 2008  
   * -   2.2  
     -   321Enable PCIe 2.0 andBeyond  support in the UEFI error records
     -   July 25, 2008  
   * -   2.2    
     -   320Clarifcation for WIN_CERTIFICATE  types & relationship with signature  database types
     -   July 25, 2008    
   * -   2.2
     -   319 UEFI IPSec protocol
     -   July 25, 2008
   * -   2.2
     -   315 EFI TCP6 Protocol
     -   July 25, 2008
   * -   2.2
     -   314 EFI MTFTP6 Protocol
     -   July 25, 2008
   * -   2.2
     -   313 EFI IPv6Configuration Protocol
     -   July 25, 2008
   * -   2.2
     -   312 EFI IPv6 Protocol
     -   July 25, 2008
   * -   2.2
     -   311EFI DHCPv6 Protocol
     -   July 25, 2008
   * -   2.2
     -   310 EFI UDPv6 Protocol
     -   July 25, 2008
   * -   2.2  
     -   309 IPv6 Address display  formatClarification
     -   July 25, 2008  
   * -   2.2  
     -   306 Some errata to the animation  support
     -   July 25, 2008  
   * -   2.2
     -   304 Errata to UpdateCapsule()
     -   July 25, 2008
   * -   2.2    
     -   303 Add ability to have aCapsule  that initiates a reset & doesn’t  return to theCaller
     -   July 25, 2008    
   * -   2.2  
     -   301 Errata to the Authentication  Protocol
     -   July 25, 2008  
   * -   2.2
     -   300 MTFTP errata
     -   July 25, 2008
   * -   2.2  
     -   299 PIWG Firmware File/Firmware  Volume Typo Errata
     -   July 25, 2008  
   * -   2.2  
     -   294 LocateDevicePath with  multi-instance device path
     -   July 25, 2008  
   * -   2.2
     -   291 HII Errata / Update
     -   July 25, 2008
   * -   2.2  
     -   288 Additional wording fixes for  GPT Entry AttributeBit 1
     -   July 25, 2008  
   * -   2.2  
     -   282 Updated Requirements Section  For ATA Pass Through (M242)
     -   July 25, 2008  
   * -   2.2  
     -   279 Firmware/OS Trusted Key  Exchange and Image Validation
     -   July 25, 2008  
   * -   2.2
     -   242 UEFI ATA Pass-Through Protocol
     -   July 25, 2008
   * -   2.2  
     -   237 UEFI User Identification  Proposal (from USST)
     -   July 25, 2008  
   * -   2.2  
     -   215 new Start() RemainingDevicePath  Syntax
     -   July 25, 2008  
   * -   2.2
     -   212 UEFI HII Standards Mapping
     -   July 25, 2008
   * -   2.2  
     -   211UEFI Setup Question / Form  Access Update
     -   July 25, 2008  
   * -   2.2
     -   210 UEFI HII Animation addition
     -   July 25, 2008
   * -   2.2
     -   202 EAP Management
     -   July 25, 2008
   * -   2.2
     -   201EAP
     -   July 25, 2008
   * -   2.2
     -   200 VLAN
     -   July 25, 2008
   * -   2.2
     -   199 FTP API
     -   July 25, 2008
   * -   2.2    
     -   198 GUID Partition Entry  AttributesClarification and  Definition
     -   July 25, 2008    
   * -   2.2
     -   169 EFI Driver Health Protocol
     -   July 25, 2008
   * -   2.2  
     -   157 Floating-Point ABIChanges For  X86, X64 & Itanium
     -   July 25, 2008  
   * -   2.1C      
     -   Re-format Revision History  fromBulleted lists to one row per  Mantis ticket/ EngineeringChange  Request
     -   June 5, 2008      
   * -   2.1C
     -   60 iSCSI Device Path Update
     -   June 5, 2008
   * -   2.1C  
     -   59 Add returnCode to Diagnostics  Protocol
     -   June 5, 2008  
   * -   2.1C  
     -   58 Language update for  EfiReservedMemory type usage
     -   June 5, 2008  
   * -   2.1C    
     -   57Clarify text for Extended SCSI  Pass Thru  Protocol.GetNextTargetLun()
     -   June 5, 2008    
   * -   2.1C
     -   56Clarification on ResetSystem
     -   June 5, 2008
   * -   2.1C
     -   55Clarification on UpdateCapsule
     -   June 5, 2008
   * -   2.1C
     -   54 ACPI Table Protocol GUID Update
     -   June 5, 2008
   * -   2.1C    
     -   52 New GUID for Driver Diagnostics  and DriverConfiguration Protocols  with new GUID
     -   June 5, 2008    
   * -   2.1C  
     -   283 Minor update toClarify a  typedef/returnCode in HII
     -   June 5, 2008  
   * -   2.1C
     -   281 Runtime memory allocation
     -   June 5, 2008
   * -   2.1C  
     -   280 Some minor errata to keyboard  related topics
     -   June 5, 2008  
   * -   2.1C    
     -   278Change references to  EFI_SIMPLE_INPUT_PROTOCOL into  EFI_SIMPLE_TEXT_INPUT_PROTOCOL
     -   June 5, 2008    
   * -   2.1C      
     -   266 PKCS11.5 structure does  notCorrectly specify the portion of  theCited RFC that pertains to  theCertificate struct/algorithm
     -   June 5, 2008      
   * -   2.1C  
     -   249 Latest update to UCST Errata  list
     -   June 5, 2008  
   * -   2.1C  
     -   248Correction to text inChapter 8.2  of UEFI 2.1B
     -   June 5, 2008  
   * -   2.1C
     -   246 New returnCode
     -   June 5, 2008
   * -   2.1C  
     -   245 Remove extraneous text  inChapter 29
     -   June 5, 2008  
   * -   2.1C    
     -   244 Replace references to  EFI_FIRMWARE_VOLUME_INFO\_ PPI with  EFI_PEI_FIRMWARE_VOLUME_INFO_PPI
     -   June 5, 2008    
   * -   2.1C  
     -   221ImageBlock Structure name typos  in 27.3.7.2
     -   June 5, 2008  
   * -   2.1C  
     -   220 Replace references to RFC 3066  to RFC 4646
     -   June 5, 2008  
   * -   2.1C  
     -   219 IA-32 and x64 stack need toBe  16-byte aligned
     -   June 5, 2008  
   * -   2.1C
     -   218 SATA update to section 9.3.5.6
     -   June 5, 2008
   * -   2.1C      
     -   217  EFI_PLATFORM_TO_DR  IVER_CONFIGURATION_PROTOCOL.Query()  Update
     -   June 5, 2008      
   * -   2.1C
     -   216 UEFI 2.1 textCorrections
     -   June 5, 2008
   * -   2.1C
     -   214 Device_IO + typos
     -   June 5, 2008
   * -   2.1C
     -   213 UEFI HII Errata
     -   June 5, 2008
   * -   2.1C  
     -   209 ESP  number/locationClarifications
     -   June 5, 2008  
   * -   2.1C
     -   208 Driver Protocol Names and GUIDs
     -   June 5, 2008
   * -   2.1C  
     -   207 Updated Wording for the File  Path
     -   June 5, 2008  
   * -   2.1C  
     -   206Clarify return values for  extended scsi passthru protocol
     -   June 5, 2008  
   * -   2.1C  
     -   203 Platform Error Record - x64  register state errata
     -   June 5, 2008  
   * -   2.1C    
     -   193 Loaded Image device paths for  EFI Drivers loaded from PCI Option  ROMs
     -   June 5, 2008    
   * -   2.1C  
     -   189 Graphics Output  ProtocolClarification
     -   June 5, 2008  
   * -   2.1B
     -   51 Long physicalBlocks updates
     -   December 11, 2007
   * -   2.1B      
     -   205Change LoadImage() parameter  name from FilePath to DevicePath;  endsConfusion with  EFI_LOADED_IMAGE_PROTOCOL
     -   December 11, 2007      
   * -   2.1B  
     -   197 EFI Loaded Image Device Path  Protocol
     -   December 11, 2007  
   * -   2.1B    
     -   190 Extensive errata form UCST  including OPCodesChanges ro  resolveConflicts.
     -   December 11, 2007    
   * -   2.1B
     -   187Clarify input protocols.
     -   December 11, 2007
   * -   2.1B  
     -   186Change PCIR struct to match PCI  FW Spec 3.0
     -   December 11, 2007  
   * -   2.1B  
     -   185Change EFI term to UEFI  forConsistency
     -   December 11, 2007  
   * -   2.1B
     -   184 SNIA/DDF Wording Update
     -   December 11, 2007
   * -   2.1B
     -   182Clarify EFI_MTFTP4_TOKEN
     -   December 11, 2007
   * -   2.1B
     -   181Correct MNP GUIDCollision
     -   December 11, 2007
   * -   2.1B  
     -   177 remove ending paragraph  (editing text) in section 9.6
     -   December 11, 2007  
   * -   2.1B
     -   175 Update to SendForm API
     -   December 11, 2007
   * -   2.1B  
     -   174 Error record addition for dma  remapping units
     -   December 11, 2007  
   * -   2.1B      
     -   173 MinorChanges to the description  of two of the fields in theCommon  Platform Error Record, in Appendix  N
     -   December 11, 2007      
   * -   2.1B
     -   172 Typo for ResetSystem()
     -   December 11, 2007
   * -   2.1B  
     -   170 (Addition of) Driver Family  Override Protocol
     -   December 11, 2007  
   * -   2.1B
     -   168 Remove LOAD_OPTION_GRAPHICS
     -   December 11, 2007
   * -   2.1B
     -   165 Fix EFI_GRAPHICS_OUTPUT_PIXEL
     -   December 11, 2007
   * -   2.1B  
     -   164 Update to USB2_HC_PROTOCOL  Table
     -   December 11, 2007  
   * -   2.1B
     -   162 UEFI PIWG Device Path Errata
     -   December 11, 2007
   * -   2.1B
     -   160Clean up references to PCIR
     -   December 11, 2007
   * -   2.1B  
     -   158 Errata to the UEFI  2.1Configuration sections
     -   December 11, 2007  
   * -   2.1B
     -   156 SendForm API Errata
     -   December 11, 2007
   * -   2.1B    
     -   159 Adjust some of the #define  names in the Simple Text Input Ex  protocol
     -   December 11, 2007    
   * -   2.1A  
     -   UEFI 2.1 incorporating Errata  through 4-27-07
     -   April 27, 2007  
   * -   2.1
     -   Second release
     -   January 23, 2007
   * -   2.0
     -   First release of specification.
     -   January 31, 2006



.. raw:: latex

   \newpage


.. _appendix-o-uefi-acpi-data-table-apx-o-uefi-acpi-table:

UEFI ACPI Data Table
=====================

To prevent ACPI namespace collision, a UEFI ACPI table format is defined. This allows creation of ACPI tables without colliding with tables reserved in the namespace.


.. _uefi-table-structure_uefi_acpi_tables:

.. list-table:: UEFI Table Structure
   :name: uefi-table-structure-apx-o-uefi-acpi-table
   :widths: 15 10 10 65


   * - **Field**
     - **Byte Length**
     - **Byte Offset**
     - **Description**
   * - Header
     - 
     - 
     - 
   * - Signature
     - 4
     - 0
     - ‘UEFI’ (0x55, 0x45, 0x46, 0x49). Signature for UEFI drivers that produce ACPI tables.
   * - Length
     - 4
     - 4
     - Length, in bytes, of the entire UEFI Table
   * - Revision
     - 1
     - 8
     - 1
   * - Checksum
     - 1
     - 9
     - Entire table must sum to zero.
   * - OEMID
     - 6
     - 10
     - OEM ID.
   * - OEM Table ID
     - 8
     - 16
     - For the UEFI Table, the table ID is the manufacture model ID.
   * - OEM Revision
     - 4
     - 24
     - OEM revision of UEFI table for supplied OEM Table ID.
   * - Creator ID
     - 4
     - 28
     - Vendor ID of utility that created the table.
   * - Creator Revision
     - 4
     - 32
     - Revision of utility that created the table.
   * - Identifier
     - 16
     - 36
     - This value contains a GUID which identifies the remaining table contents.
   * - DataOffset
     - 2
     - 52
     - Specifies the byte offset to the remaining data in the UEFI table.
   * - Data
     - X
     - DataOffset
     - Contains the rest of the UEFI table contents


The first use of this UEFI ACPI table format is the SMM Communication ACPI Table. This table describes a special software SMI that can be used to initiate inter-mode communication in the OS present environment by non-firmware agents with SMM code.

**NOTE**: *The use of the SMM Communication ACPI table is deprecated in UEFI spec. 2.7. This is due to the lack of a use case for inter-mode communication by non-firmware agents with SMM code and support for initiating this form of communication in common OSes*.



.. _smm-communication-acpi-table._uefi_acpi_tables:

.. list-table:: SMM Communication ACPI Table.
   :name: smm-communication-acpi-table-apx-o-uefi-acpi-table
   :widths: 15 10 10 45
   :class: longtable

   * - **Field**
     - **Byte Length**
     - **Byte Offset**
     - **Description**
   * - Signature
     - 4
     - 0
     - ‘UEFI’ (0x55, 0x45, 0x46, 0x49) Signature for UEFI drivers that produce ACPI tables.
   * - Length
     - 4
     - 4
     - 66+N. Length, in bytes, of the entire Table. N is a length of the optional implementation specific data that can be included in this table.
   * - Revision
     - 1
     - 8
     - 2
   * - Checksum
     - 1
     - 9
     - Entire table must sum to zero.
   * - OEMID
     - 6
     - 10
     - OEM ID.
   * - OEM Table ID
     - 8
     - 16
     - For the UEFI Table, the table ID is the manufacturer model ID.
   * - OEM Revision
     - 4
     - 24
     - OEM revision of UEFI table for supplied OEM Table ID.
   * - Creator ID
     - 4
     - 28
     - Vendor ID of utility that created the table.
   * - Creator Revision
     - 4
     - 32
     - Revision of utility that created the table.
   * - Identifier
     - 16
     - 36
     - GUID {0xc68ed8e2, 0x9dc6, 0x4cbd, 0x9d, 0x94, 0xdb, 0x65, \\ 0xac, 0xc5, 0xc3, 0x32}
   * - DataOffset
     - 2
     - 52
     - Must be 54 for this version of the specification. Specifies the byte offset of the *SW SMI Number* field, relative to the start of this table. Future expansion may place additional fields between *DataOffset* and *SW SMI Number* , so this offset should always be used to calculate the location of *SW SMI Number* .
   * - SW SMI Number
     - 4
     - 54
     - Number to write into software SMI triggering port.
   * - Buffer Ptr Address
     - 8
     - 58
     - Address of the communication buffer pointer. The pointer address (this field) and the pointer value (the actual address of the communication buffer) are 64-bit physical addresses.  The creator of this table must initialize pointer value with 0. The communication buffer must begin with the *EFI_SMM_COMM UNICATE_HEADER* defined in the "Related Definitions" section below. The communication buffer must be physically contiguous.
   * - Invocation register
     - 12
     - 66
     - Generic Address Structure (GAS) which provides the address of a register that must be written to with the address of a communication buffer to invoke a management mode service. Using this method of invocation is optional, and if not present this span of the table should be populated with zeros. See ACPI6.0 "Generic Address Structure"


.. _invocation-method_uefi_acpi_tables:

Invocation method
*****************

There are two methods of invocation provided by this specification:

**1. Using invocation register**

If the invocation register is non-zero, this then this method takes precedence and the SW SMI number field and DataOffset fields must be ignored. The invocation register entry provides the address of a register that must be written to in order to invoke the SMM service. The caller must write the communication buffer address into the register. This will cause an SMM invocation. Upon return from the SMM service call the value in the register provides a return error codes from the SMM invocation. See PI/SMM Vol 4 version xx.yy *EFI_SMM_COMMUNICATION_PROTOCOL.Communicate* function for valid error codes. 

The invocation address field uses generic address structure to specify the register address. GAS allows the address space of the register to be Functional Fixed Hardware (FFH). If this address space is used please refer to CPU architecture specific documentation for ascertaining how the write to the register should be performed. For more details on the GAS format please see the *ACPI Specification* . 

Note that for implementations that support concurrent invocation of SMM from multiple processors, the register provided must be a per processor register. In such implementation, the calling execution context must not migrate from one CPU to another between writing to the register, to make the SMM call, and reading the value of the register, to read the error return code. 


**2. Using the SW SMI number**

This method is specific to x86 CPUs .

In order to initiate inter-mode communication OS present agent has to perform the following tasks: 

-  Prepare communication data buffer that starts with the *EFI_SMM_COMMUNICATE_HEADER* .
-  Check the value of the communication buffer pointer (a value at the address specified by the Buffer Ptr Address field). If the pointer's value is zero, update it with the address of the communication buffer. If the pointer's value is non-zero, another inter-mode communication transaction is in progress, and the current communication attempt has to be postponed or canceled. 

**NOTE**: *These steps must be performed as an atomic transaction. For example, on IA-32/x64 platforms this can be done using the CMPXCHG CPU instruction*.

-  Generate software SMI using value from the SMM Communication ACPI Table. The actual means of generating the software SMI is platform-specific.
-  Set communication buffer pointer's value to zero.


**Related Definitions**

.. code-block::

  
   typedef struct {
     EFI_GUID             HeaderGuid;
     UINTN                MessageLength;
     UINT8                Data[ANYSIZE_ARRAY];
   }   EFI_SMM_COMMUNICATE_HEADER;
  


HeaderGuid
  Allows for disambiguation of the message format. Type *EFI_GUID* is defined in *InstallProtocolInterface()* .

MessageLength
  Describes the size of *Data* (in bytes) and does not include the size of the header.

Data
  Designates an array of bytes that is *MessageLength* in size



.. _protocols-acpi-protocols:

Protocols — ACPI Protocols
===========================


.. _efi-acpi-table-protocol:

EFI_ACPI_TABLE_PROTOCOL
#######################


**Summary**

This protocol may be used to install or remove an ACPI table
from a platform.


**GUID**

.. code-block::

   #define EFI_ACPI_TABLE_PROTOCOL_GUID \
     {0xffe06bdd, 0x6107, 0x46a6,\
       {0x7b, 0xb2, 0x5a, 0x9c, 0x7e, 0xc5, 0x27, 0x5c}}


**Protocol Interface Structure**

.. code-block::

   typedef struct _EFI_ACPI_TABLE_PROTOCOL {
     EFI_ACPI_TABLE_INSTALL_ACPI_TABLE       InstallAcpiTable;
     EFI_ACPI_TABLE_UNINSTALL_ACPI_TABLE     UninstallAcpiTable;
   }  EFI_ACPI_TABLE_PROTOCOL;


**Parameters**

InstallAcpiTable
  Installs an ACPI table into the system.

UninstallAcpiTable
  Removes a previously installed ACPI table from the system.


**Description**

The *EFI_ACPI_TABLE_PROTOCOL* provides the ability for a component to install and uninstall ACPI tables from a platform.


.. _efi-acpi-table-protocol-installacpitable:

EFI_ACPI_TABLE_PROTOCOL.InstallAcpiTable()
##########################################


**Summary**

Installs an ACPI table into the RSDT/XSDT.


**Prototype**

.. code-block:: 
  
   typedef  
   EFI_STATUS  
   (EFIAPI *EFI_ACPI_TABLE_INSTALL_ACPI_TABLE) (  
     IN EFI_ACPI_TABLE_PROTOCOL                   *This,  
     IN VOID                                      *AcpiTableBuffer,  
     IN UINTN                                     AcpiTableBufferSize,  
     OUT UINTN                                    *TableKey,  
     );


**Parameters**

This
  A pointer to a `EFI_ACPI_TABLE_PROTOCOL`_ .

AcpiTableBuffer
  A pointer to a buffer containing the ACPI table to be installed.

AcpiTableBufferSize
  Specifies the size, in bytes, of the *AcpiTableBuffer* buffer.

TableKey
  Returns a key to refer to the ACPI table.


**Description**

The *InstallAcpiTable()* function allows a caller to install an ACPI table. The ACPI table may either by a System Description Table or the FACS. For all tables except for the DSDT and FACS, a copy of the table will be linked by the RSDT/XSDT. For the FACS and DSDT, the pointer to a copy of the table will be updated in the FADT, if present. 

To prevent namespace collision, ACPI tables may be created using UEFI ACPI table format,  :ref:`appendix-o-uefi-acpi-data-table-apx-o-uefi-acpi-table`. If this protocol is used to install a table with a signature already present in the system, the new table will not replace the existing table. It is a platform implementation decision to add a new table with a signature matching an existing table or disallow duplicate table signatures and return *EFI_ACCESS_DENIED*. 

On successful output, *TableKey* is initialized with a unique key. Its value may be used in a subsequent call to *UninstallAcpiTable* to remove an ACPI table.   

On successful output, the *EFI_ACPI_TABLE_PROTOCOL* will ensure that the checksum field is correct for both the RSDT/XSDT table and the copy of the table being installed that is linked by the RSDT/XSDT. 

On successful completion, this function reinstalls the relevant *EFI_CONFIGURATION_TABLE* pointer to the RSDT.


**Status Codes Returned**

.. list-table::
   :widths: 35 70

   * - EFI_SUCCESS
     - The table was successfully inserted
   * - EFI_INVALID_PARAMETER
     - The *AcpiTableBuffer* is *NULL* , the *TableKey* is *NULL* ;the *AcpiTableBufferSize* , and the size field embedded in the ACPI table pointed to by *AcpiTableBuffer* are not in sync.
   * - EFI_OUT_OF_RESOURCES
     - Insufficient resources exist to complete the request.
   * - EFI_ACCESS_DENIED
     - The table signature matches a table already present in the system and platform policy does not allow duplicate tables of this type.


.. _efi-acpi-table-protocol-uninstallacpitable:

EFI_ACPI_TABLE_PROTOCOL.UninstallAcpiTable()
############################################


**Summary**

Removes an ACPI table from the RSDT/XSDT.


**Prototype**


.. code-block:: 
  
   typedef  
   EFI_STATUS  
   (EFIAPI *EFI_ACPI_TABLE_UNINSTALL_ACPI_TABLE) (  
     IN EFI_ACPI_TABLE_PROTOCOL             *This,  
     IN UINTN                               TableKey,  
     );


**Parameters**

This
  A pointer to a `EFI_ACPI_TABLE_PROTOCOL`_ .

TableKey
  Specifies the table to uninstall. The key was returned from *InstallAcpiTable()*.


**Description**

The *UninstallAcpiTable()* function allows a caller to remove an ACPI table. The routine will remove its reference from the RSDT/XSDT. A table is referenced by the TableKey parameter returned from a prior call to *InstallAcpiTable()*. 

On successful completion, this function reinstalls the relevant *EFI_CONFIGURATION_TABLE* pointer to the RSDT.


**Status Codes Returned**

.. list-table::
   :widths: 35 70

   * - EFI_SUCCESS
     - The table was successfully inserted
   * - EFI_NOT_FOUND
     - TableKey does not refer to a valid key for a table entry.
   * - EFI_OUT_OF_RESOURCES
     - Insufficient resources exist to complete the request.
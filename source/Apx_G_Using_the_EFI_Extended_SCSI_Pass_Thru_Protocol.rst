
.. appendix-g-using-the-efi-extended-scsi-pass-thru-protocol-apx-g-using-efi-scsi-pass-thru-protocol:

Using the EFI Extended SCSI Pass Thru Protocol
===============================================


This appendix describes how an EFI utility might gain access to the EFI SCSI Pass Thru interfaces. The basic concept is to use the :ref:`efi-boot-services-locatehandle`  boot service to retrieve the list of handles that support the  :ref:`efi-ext-scsi-pass-thru-protocol` . Each of these handles represents a different SCSI channel present in the system. Each of these handles can then be used the retrieve the *EFI_EXT_SCSI_PASS_THRU_PROTOCOL* interface with the  :ref:`efi-boot-services-handleprotocol`  boot service. The *EFI_EXT_SCSI_PASS_THRU_PROTOCOL* interface provides the services required to access any of the SCSI devices attached to a SCSI channel. The services of the *EFI_EXT_SCSI_PASS_THRU_PROTOCOL* are then to loop through the Target IDs of all the SCSI devices on the SCSI channel.


.. code-block::

  
   #include "efi.h"
   #include "efilib.h"

   #include EFI_PROTOCOL_DEFINITION(ExtScsiPassThru)

   EFI_GUID gEfiExtScsiPassThruProtocolGuid =
   EFI_EXT_SCSI_PASS_THRU_PROTOCOL_GUID;

   EFI_STATUS
   UtilityEntryPoint(
     EFI_HANDLE ImageHandle,
     EFI_SYSTEM_TABLE SystemTable
     )
   {
     EFI_STATUS Status;
     UINTN            NoHandles;
     EFI_HANDLE       *HandleBuffer;
     UINTN            Index;
     EFI_EXT_SCSI_PASS_THRU_PROTOCOL *ExtScsiPassThruProtocol;

     //
     // Initialize EFI Library
     //
     InitializeLib (ImageHandle, SystemTable);

     //
     // Get list of handles that support the
     // EFI_EXT_SCSI_PASS_THRU_PROTOCOL
     //
     NoHandles = 0;
     HandleBuffer = NULL;
     Status = LibLocateHandle(
                     ByProtocol,
                     &gEfiExtScsiPassThruProtocolGuid,
                     NULL,
                     &NoHandles,
                     &HandleBuffer
                     );
     if (EFI_ERROR(Status)) {
      BS->Exit(ImageHandle,EFI_SUCCESS,0,NULL);
     }

     //
     // Loop through all the handles that support
     // EFI_EXT_SCSI_PASS_THRU
     //
     for (Index = 0; Index < NoHandles; Index++) {

       //
       // Get the EFI_EXT_SCSI_PASS_THRU_PROTOCOL Interface
       // on each handle
       //
       BS->HandleProtocol(
                     HandleBuffer[Index],
                     &gEfiExtScsiPassThruProtocolGuid,
                     (VOID **)&ExtScsiPassThruProtocol
                     );

     if (!EFI_ERROR(Status)) {

       //
       // Use the EFI_EXT_SCSI_PASS_THRU Interface to
       // perform tests
       //
       Status = DoScsiTests(ScsiPassThruProtocol);
      }
     }
    return EFI_SUCCESS;
   }

   EFI_STATUS
   DoScsiTests(
    EFI_EXT_SCSI_PASS_THRU_PROTOCOL *ExtScsiPassThruProtocol
    )

   {
     EFI_STATUS         Status;
     UINT32             Target;
     UINT64             Lun;
     EFI_EXT_SCSI_PASS_THRU_SCSI_REQUEST_PACKET Packet;
     EFI_EVENT          Event;

     //
     // Get first Target ID and LUN on the SCSI channel
     //
     Target = 0xffffffff;
     Lun = 0;
     Status = ExtScsiPassThruProtocol-> GetNextTargetLun(
                     ExtScsiPassThruProtocol,
                     &Target,
                     &Lun
                     );

     //
     // Loop through all the SCSI devices on the SCSI channel
     //
     while (!EFI_ERROR (Status)) {

       //
       // Blocking I/O example.
       // Fill in Packet before calling PassThru()
       //
       Status = ExtScsiPassThruProtocol->PassThru(
                       ExtScsiPassThruProtocol,
                       Target,
                       Lun,
                       &Packet,
                       NULL
                       );

       //
       // Non Blocking I/O
       // Fill in Packet and create Event before calling PassThru()
       //
       Status = ExtScsiPassThruProtocol->PassThru(
                       ExtScsiPassThruProtocol,
                       Target,
                       Lun,
                       &Packet,
                       &Event
                       );

       //
       // Get next Target ID and LUN on the SCSI channel
       //
       Status = ExtScsiPassThruProtocol-> GetNextTargetLun(
                       ExtScsiPassThruProtocol,
                       &Target,
                       &Lun
                       );
      }

    return EFI_SUCCESS;
   }
  

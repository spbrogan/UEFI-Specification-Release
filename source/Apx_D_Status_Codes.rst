
.. _appendix-d-status-codes-apx-d-status-codes:

Status Codes
==============

EFI interfaces return an *EFI_STATUS* code.    See  :ref:`efi-status-success-codes-high-bit-clear-apx-d-status-codes` ,   :ref:`efi-status-error-codes-high-bit-set-apx-d-status-codes` ,   :ref:`efi-status-warning-codes-high-bit-clear-apx-d-status-codes` list these codes for success, errors, and warnings, respectively. The range of status codes that have the highest bit set and the next to highest bit clear are reserved for use by EFI. The range of status codes that have both the highest bit set and the next to highest bit set are reserved for use by OEMs. Success and warning codes have their highest bit clear, so all success and warning codes have positive values. The range of status codes that have both the highest bit clear and the next to highest bit clear are reserved for use by EFI. The range of status code that have the highest bit clear and the next to highest bit set are reserved for use by OEMs.  The Table below lists the status code ranges described above.



.. list-table:: EFI_STATUS Code Ranges
   :name: efi-status-code-ranges-apx-d-status-codes
   :widths: 15 30 45
   :class: longtable

   * - **Supported 32-bit Range**
     - **Supported 64-bit Architecture Ranges**
     - **Description**
   * - 0x00000000-0x1fffffff
     - 0x00000000000000 00-0x1fffffffffffffff
     - Warning codes reserved for use by UEFI main specification.
   * - 0x20000000-0x3fffffff
     - 0x20000000000000 00-0x3fffffffffffffff
     - Warning codes reserved for use by the Platform Initialization Architecture Specification.
   * - 0x40000000- 0x7fffffff
     - 0x4000000000000000- 0x7fffffffffffffff
     - Warning codes reserved for OEM usage.
   * - 0x80000000-0x9fffffff
     - 0x80000000000000 00-0x9fffffffffffffff
     - Error codes reserved for use by UEFI main spec.
   * - 0xa0000000-0xbfffffff
     - 0xa0000000000000 00-0xbfffffffffffffff
     - Error codes reserved for use by the Platform Initialization Architecture Specification.
   * - 0xc0000000- 0xffffffff
     - 0xc000000000000000- 0xcfffffffffffffff
     - Error codes reserved for OEM usage.





.. list-table:: EFI_STATUS Success Codes (High Bit Clear)
   :name: efi-status-success-codes-high-bit-clear-apx-d-status-codes
   :widths: 35 10 45

   * - **Mnemonic**    
     - **Value** 
     - **Description**
   * - EFI_SUCCESS 
     - 0     
     - The operation completed successfully.




.. list-table:: EFI_STATUS Error Codes (High Bit Set)
   :name: efi-status-error-codes-high-bit-set-apx-d-status-codes
   :widths: 35 10 45
   :class: longtable

   * - **Mnemonic**
     - **Value**
     - **Description**
   * - EFI_LOAD_ERROR
     - 1
     - The image failed to load.
   * - EFI_INVALID_PARAMETER
     - 2
     - A parameter was incorrect.
   * - EFI_UNSUPPORTED
     - 3
     - The operation is not supported.
   * - EFI_BAD_BUFFER_SIZE
     - 4
     - The buffer was not the proper size for the request.
   * - EFI_BUFFER_TOO_SMALL
     - 5
     - The buffer is not large enough to hold the requested data. The required buffer size is returned in the appropriate parameter when this error occurs.
   * - EFI_NOT_READY
     - 6
     - There is no data pending upon return.
   * - EFI_DEVICE_ERROR
     - 7
     - The physical device reported an error while attempting the operation.
   * - EFI_WRITE_PROTECTED
     - 8
     - The device cannot be written to.
   * - EFI_OUT_OF_RESOURCES
     - 9
     - A resource has run out.
   * - EFI_VOLUME_CORRUPTED
     - 10
     - An inconstancy was detected on the file system causing the operating to fail.
   * - EFI_VOLUME_FULL
     - 11
     - There is no more space on the file system.
   * - EFI_NO_MEDIA
     - 12
     - The device does not contain any medium to perform the operation.
   * - EFI_MEDIA_CHANGED
     - 13
     - The medium in the device has changed since the last access.
   * - EFI_NOT_FOUND
     - 14
     - The item was not found.
   * - EFI_ACCESS_DENIED
     - 15
     - Access was denied.
   * - EFI_NO_RESPONSE
     - 16
     - The server was not found or did not respond to the request.
   * - EFI_NO_MAPPING
     - 17
     - A mapping to a device does not exist.
   * - EFI_TIMEOUT
     - 18
     - The timeout time expired.
   * - EFI_NOT_STARTED
     - 19
     - The protocol has not been started.
   * - EFI_ALREADY_STARTED
     - 20
     - The protocol has already been started.
   * - EFI_ABORTED
     - 21
     - The operation was aborted.
   * - EFI_ICMP_ERROR
     - 22
     - An ICMP error occurred during the network operation.
   * - EFI_TFTP_ERROR
     - 23
     - A TFTP error occurred during the network operation.
   * - EFI_PROTOCOL_ERROR
     - 24
     - A protocol error occurred during the network operation.
   * - EFI_INCOMPATIBLE_VERSION
     - 25
     - The function encountered an internal version that was incompatible with a version requested by the caller.
   * - EFI_SECURITY_VIOLATION
     - 26
     - The function was not performed due to a security violation.
   * - EFI_CRC_ERROR
     - 27
     - A CRC error was detected.
   * - EFI_END_OF_MEDIA
     - 28
     - Beginning or end of media was reached
   * - EFI_END_OF_FILE
     - 31
     - The end of the file was reached.
   * - EFI_INVALID_LANGUAGE
     - 32
     - The language specified was invalid.
   * - EFI_COMPROMISED_DATA
     - 33
     - The security status of the data is unknown or compromised and the data must be updated or replaced to restore a valid security status.
   * - EFI_IP_ADDRESS_CONFLICT
     - 34
     - There is an address conflict address allocation
   * - EFI_HTTP_ERROR
     - 35
     - A HTTP error occurred during the network operation.



.. list-table:: EFI_STATUS Warning Codes (High Bit Clear)
   :name: efi-status-warning-codes-high-bit-clear-apx-d-status-codes
   :widths: 35 10 45
   :class: longtable

   * - **Mnemonic**
     - **Value**
     - **Description**
   * - EFI_WARN_UNKNOWN_GLYPH
     - 1
     - The string contained one or more characters that the device could not render and were skipped.
   * - EFI_WARN_DELETE_FAILURE
     - 2
     - The handle was closed, but the file was not deleted.
   * - EFI_WARN_WRITE_FAILURE
     - 3
     - The handle was closed, but the data to the file was not flushed properly.
   * - EFI_WARN_BUFFER_TOO_SMALL
     - 4
     - The resulting buffer was too small, and the data was truncated to the buffer size.
   * - EFI_WARN_STALE_DATA
     - 5
     - The data has not been updated within the timeframe set by local policy for this type of data.
   * - EFI_WARN_FILE_SYSTEM
     - 6
     - The resulting buffer contains UEFI-compliant file system.
   * - EFI_WARN_RESET_REQUIRED
     - 7
     - The operation will be processed across a system reset.





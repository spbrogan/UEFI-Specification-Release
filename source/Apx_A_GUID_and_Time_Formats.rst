.. raw:: latex
  
  \setcounter{table}{0}
  \renewcommand{\thetable}{\Alph{chapter}.\arabic{table}}
  \setcounter{figure}{0}
  \renewcommand{\thefigure}{\Alph{chapter}.\arabic{figure}}

.. _appendix-a-guid-and-time-formats-apx-a-guid-and-time-formats:

GUID and Time Formats
======================

All EFI GUIDs (Globally Unique Identifiers) have the format described in RFC 4122 and comply with the referenced algorithms for generating GUIDs. It should also be noted that TimeLow, TimeMid, TimeHighAndVersion fields in the EFI are encoded as little endian. The following table defines the format of an EFI GUID (128 bits).

.. list-table:: EFI GUID Format
   :name: efi-guid-format-apxA-guid-and-time-formats
   :widths: 15 10 10 65
   :class: longtable

   * - **Mnemonic**
     - **Byte Offset**
     - **Byte Length**
     - **Description**
   * - TimeLow
     - 0
     - 4
     - The low field of the timestamp.
   * - TimeMid
     - 4
     - 2
     - The middle field of the timestamp.
   * - TimeHighAndVersion
     - 6
     - 2
     - The high field of the timestamp multiplexed with the version number.
   * - ClockSeqHighAndReserved
     - 8
     - 1
     - The high field of the clock sequence multiplexed with the variant.
   * - ClockSeqLow
     - 9
     - 1
     - The low field of the clock sequence.
   * - Node
     - 10
     - 6
     - The spatially unique node identifier. This can be based on any IEEE 802 address obtained from a network card. If no network card exists in the system, a crypto graphic-quality random number can be used.


This appendix for GUID defines a 60-bit timestamp format that is used to generate the GUID. All EFI time information is stored in 64-bit structures that contain the following format: The timestamp is a 60-bit value containing a count of 100-nanosecond intervals since 00:00:00.00, 15 October 1582 (the date of Gregorian reform to the Christian calendar). This time value will not roll over until the year 3400 AD. It is assumed that a future version of the EFI specification can deal with the year-3400 issue by extending this format if necessary. 

This specification also defines a standard text representation of the GUID. This format is also sometimes called the "registry format". It consists of 36 characters, as follows:

.. code-block::

   aabbccdd-eeff-gghh-iijj-kkllmmnnoopp:


The pairs *aa* - *pp* are two characters in the range ‘0’-‘9’, ‘a’-‘f’ or ‘A’-F’, with each pair representing a single byte hexadecimal value.

The following table describes the relationship between the text representation and a 16-byte buffer, the structure defined in :ref:`efi-guid-format-apxA-guid-and-time-formats` and the EFI_GUID structure.



.. list-table:: Text representation relationships
   :name: text-representation-relationships-apxA-guid-and-time-formats
   :widths: 5 5 30 30
   :class: longtable

   * - String
     - Offset In Buffer
     - Relationship to :ref:`efi-guid-format-apxA-guid-and-time-formats` 
     - Relationship To EFI_GUID
   * - *aa*
     - 3
     - TimeLow[24:31]
     - Data1[24:31]
   * - *bb*
     - 2
     - TimeLow[16:23]
     - Data1[16:23]
   * - *cc*
     - 1
     - TimeLow[8:15]
     - Data1[8:15]
   * - *dd*
     - 0
     - TimeLow[0:7]
     - Data1[0:7]
   * - *ee*
     - 5
     - TimeMid[8:15]
     - Data2[8:15]
   * - *ff*
     - 4
     - TimeMid[0:7]
     - Data2[0:7]
   * - *gg*
     - 7
     - TimeHigh AndVersion[8:15]
     - Data3[8:15]
   * - *hh*
     - 6
     - TimeHig hAndVersion[0:7]
     - Data3[0:7]
   * - *ii*
     - 8
     - ClockSeqHigh AndReserved[0:7]
     - Data4[0:7]
   * - *jj*
     - 9
     - ClockSeqLow[0:7]
     - Data4[8:15]
   * - *kk*
     - 10
     - Node[0:7]
     - Data4[16:23]
   * - *ll*
     - 11
     - Node[8:15]
     - Data4[24:31]
   * - *mm*
     - 12
     - Node[16:23]
     - Data4[32:39]
   * - *nn*
     - 13
     - Node[24:31]
     - Data4[40:47]
   * - *oo*
     - 14
     - Node[32:39]
     - Data4[48:55]
   * - *pp*
     - 15
     - Node[40:47]
     - Data4[56:63]

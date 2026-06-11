

.. _Appendix-M-formats-language-codes-and-language-code-arrays-apx-m-formats-language-codes-and-language-code-arrays:

Formats — Language Codes and Language Code Arrays
===================================================


This appendix lists the formats for language codes and language code arrays.


.. _specifying-individual-language-codes_formats_language_codes_and_language_code_arrays:

Specifying individual language codes
------------------------------------

The preferred representation of a language code is done via an RFC 4646 language code identifier*.

.. _alias-codes-supported-in-addition-to-rfc-4646_formats_language_codes_and_language_code_arrays:


**Alias codes supported in addition to RFC 4646**

.. list-table:: Alias Codes Supported in Addition to RFC 4646
   :widths: 15 45
   :name: alias-codes-supported-in-addition-to-rfc-4646

   * - **RFC string** 
     - **Supported Alias String**
   * - zh-Hans
     - zh-chs
   * - zh-Hant
     - zh-cht

An RFC 4646 language code is represented as a null-terminated ASCII string.

An RFC 4646 language string must be constructed according to the tag creation rules in section 2.3 of RFC 4646. For example, when constructing the primary language tag for a locale identifier, if a 2 character ISO 639-1 language code exists along with a 3 character ISO 639-2 language code, then the ISO 639-1 language code must be used. Further, if an ISO 639-1 tag does not exist, then the ISO 639-2/T (Terminology) tag must be for the primary locale before an ISO 639-2/B (Bibliographic) tag may be used. See RFC 4646 for a complete discussion of this topic. 


.. _specifying-language-code-arrays_formats_language_codes_and_language_code_arrays:

Specifying language code arrays:
################################

Native RFC 4646 format array:

An array of RFC 4646 character codes is represented as a NULL terminated char8 array of RFC 4646 language code strings. Each of these strings is delimited by a semicolon (';') character. For example, an array of US English and Traditional Chinese would be represented as the NULL-terminated string "en-us;zh-Hant". 

.. _appendix-j-efi-byte-code-virtual-machine-opcode-list-apx-j-efi-byte-code-virtual-machine-opcode-list:

EFI Byte Code Virtual Machine Opcode List
===========================================

The following table lists the opcodes for EBC instructions. Note that opcodes only require 6 bits of the opcode byte of EBC instructions. The other two bits are used for other encodings that are dependent on the particular instruction.

.. _ebc-virtual-machine-opcode-summary-efi-byte-code-virtual-machine-opcode-list:



.. list-table:: EBC Virtual Machine Opcode Summary
   :name: ebc-virtual-machine-opcode-summary
   :widths: 15 75

   * - **Opcode**
     - **Description**
   * - 0x00
     - :ref:`break-efi-byte-code-virtual-machine` [break code]
   * - 0x01
     - :ref:`jmp-efi-byte-code-virtual-machine` \ 32{cs {@}R1 {Immed32 
   * - 0x02
     - :ref:`jmp8-efi-byte-code-virtual-machine` \ {cs Immed8
   * - 0x03
     - :ref:`call-efi-byte-code-virtual-machine` \ 32{EX}{a} {@}R1 {Immed32 
   * - 0x04
     - :ref:`ret-efi-byte-code-virtual-machine`
   * - 0x05
     - :ref:`cmp-efi-byte-code-virtual-machine` \ [32 R1, {@}R2 {Index16
   * - 0x06
     - :ref:`cmp-efi-byte-code-virtual-machine` \ [32 R1, {@}R2 {Index16
   * - 0x07
     - :ref:`cmp-efi-byte-code-virtual-machine` \ [32 R1, {@}R2 {Index16
   * - 0x08
     - :ref:`cmp-efi-byte-code-virtual-machine` \ [32 R1, {@}R2 {Index16
   * - 0x09
     - :ref:`cmp-efi-byte-code-virtual-machine` \ [32 R1, {@}R2 {Index16
   * - 0x0A
     - :ref:`not-efi-byte-code-virtual-machine` \ [32 {@}R1, {@}R2 {Index16
   * - 0x0B
     - :ref:`neg-efi-byte-code-virtual-machine` \ [32 {@}R1,{@}R2 {Index16
   * - 0x0C
     - :ref:`add-efi-byte-code-virtual-machine` \ [32 {@}R1,{@}R2 {Index16
   * - 0x0D
     - :ref:`sub-efi-byte-code-virtual-machine` \ [32 {@}R1,{@}R2 {Index16
   * - 0x0E
     - :ref:`mul-efi-byte-code-virtual-machine` \ [32 {@}R1,{@}R2 {Index16
   * - 0x0F
     - :ref:`mulu-efi-byte-code-virtual-machine` \ [32 {@}R1,{@}R2 {Index16
   * - 0x10
     - :ref:`div-efi-byte-code-virtual-machine` \ [32 {@}R1,{@}R2 {Index16
   * - 0x11
     - :ref:`divu-efi-byte-code-virtual-machine` \ [32 {@}R1,{@}R2 {Index16
   * - 0x12
     - :ref:`mod-efi-byte-code-virtual-machine` \ [32 {@}R1,{@}R2 {Index16
   * - 0x13
     - :ref:`modu-efi-byte-code-virtual-machine` \ [32 {@}R1,{@}R2 {Index16
   * - 0x14
     - :ref:`and-efi-byte-code-virtual-machine` \ [32 {@}R1,{@}R2 {Index16
   * - 0x15
     - :ref:`or-efi-byte-code-virtual-machine` \ [32 {@}R1,{@}R2 {Index16
   * - 0x16
     - :ref:`xor-efi-byte-code-virtual-machine` \ [32 {@}R1,{@}R2 {Index16
   * - 0x17
     - :ref:`shl-efi-byte-code-virtual-machine` \ [32 {@}R1,{@}R2 {Index16
   * - 0x18
     - :ref:`shr-efi-byte-code-virtual-machine` \ [32 {@}R1,{@}R2 {Index16
   * - 0x19
     - :ref:`ashr-efi-byte-code-virtual-machine` \ [32 {@}R1,{@}R2 {Index16
   * - 0x1A
     - :ref:`extndb-efi-byte-code-virtual-machine` \ [32 {@}R1, {@}R2 {Index16
   * - 0x1B
     - :ref:`extndw-efi-byte-code-virtual-machine` \ [32 {@}R1,{@}R2 {Index16
   * - 0x1C
     - :ref:`extndd-efi-byte-code-virtual-machine` \ [32 {@}R1,{@}R2 {Index16
   * - 0x1D
     - :ref:`mov-efi-byte-code-virtual-machine` \ bw {@}R1 {Index16}, {@}R2 {Index16}
   * - 0x1E
     - :ref:`mov-efi-byte-code-virtual-machine` \ ww {@}R1 {Index16}, {@}R2 {Index16}
   * - 0x1F
     - :ref:`mov-efi-byte-code-virtual-machine` \ dw {@}R1 {Index16}, {@}R2 {Index16}
   * - 0x20
     - :ref:`mov-efi-byte-code-virtual-machine` \ qw {@}R1 {Index16}, {@}R2 {Index16}
   * - 0x21
     - :ref:`mov-efi-byte-code-virtual-machine` \ bd {@}R1 {Index32}, {@}R2 {Index32}
   * - 0x22
     - :ref:`mov-efi-byte-code-virtual-machine` \ wd {@}R1 {Index32}, {@}R2 {Index32}
   * - 0x23
     - :ref:`mov-efi-byte-code-virtual-machine` \ dd {@}R1 {Index32}, {@}R2 {Index32}
   * - 0x24
     - :ref:`mov-efi-byte-code-virtual-machine` \ qd {@}R1 {Index32}, {@}R2 {Index32}
   * - 0x25
     - :ref:`movsn-efi-byte-code-virtual-machine` \ w {@}R1 {Index16}, {@}R2 {Index16
   * - 0x26
     - :ref:`movsn-efi-byte-code-virtual-machine` \ d {@}R1 {Index32}, {@}R2 {Index32
   * - 0x27
     - Reserved
   * - 0x28
     - :ref:`mov-efi-byte-code-virtual-machine` \ qq {@}R1 {Index64}, {@}R2 {Index64}
   * - 0x29
     - :ref:`loadsp-efi-byte-code-virtual-machine` [Flags], R2
   * - 0x2A
     - :ref:`storesp-efi-byte-code-virtual-machine` R1, [IP|Flags]
   * - 0x2B
     - :ref:`push-efi-byte-code-virtual-machine` \ [32 {@}R1 {Index16
   * - 0x2C
     - :ref:`pop-efi-byte-code-virtual-machine` \ [32 {@}R1 {Index16
   * - 0x2D
     - :ref:`cmpi-efi-byte-code-virtual-machine` \ [32 {@}R1 {Index16}, Immed16
   * - 0x2E
     - :ref:`cmpi-efi-byte-code-virtual-machine` \ [32 {@}R1 {Index16}, Immed16
   * - 0x2F
     - :ref:`cmpi-efi-byte-code-virtual-machine` \ [32 {@}R1 {Index16}, Immed16
   * - 0x30
     - :ref:`cmpi-efi-byte-code-virtual-machine` \ [32 {@}R1 {Index16}, Immed16
   * - 0x31
     - :ref:`cmpi-efi-byte-code-virtual-machine` \ [32 {@}R1 {Index16}, Immed16
   * - 0x32
     - :ref:`movn-efi-byte-code-virtual-machine` \ w {@}R1 {Index16}, {@}R2 {Index16}
   * - 0x33
     - :ref:`movn-efi-byte-code-virtual-machine` \ d {@}R1 {Index32}, {@}R2 {Index32}
   * - 0x34
     - Reserved
   * - 0x35
     - :ref:`pushn-efi-byte-code-virtual-machine` {@}R1 {Index16
   * - 0x36
     - :ref:`popn-efi-byte-code-virtual-machine` {@}R1 {Index16
   * - 0x37
     - :ref:`movi-efi-byte-code-virtual-machine` \ [b {@}R1 {Index16}, Immed16
   * - 0x38
     - :ref:`movin-efi-byte-code-virtual-machine` \ [w {@}R1 {Index16}, Index16
   * - 0x39
     - :ref:`movrel-efi-byte-code-virtual-machine` \ [w {@}R1 {Index16}, Immed16
   * - 0x3A
     - Reserved
   * - 0x3B
     - Reserved
   * - 0x3C
     - Reserved
   * - 0x3D
     - Reserved
   * - 0x3E
     - Reserved
   * - 0x3F
     - Reserved





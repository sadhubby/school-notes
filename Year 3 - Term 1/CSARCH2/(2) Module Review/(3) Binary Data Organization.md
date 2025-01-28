
Binary digits also known as bits, can group to form various organizations

 

| Organization       | Number of bits   | Usage                                            |
| ------------------ | ---------------- | ------------------------------------------------ |
| Bit (binary digit) | 2 cells - 0 or 1 | Basic Unit                                       |
| Crumb              | 2 bits           | largely defunct term, rarely used                |
| Nibble             | 4 bits           | Hex digit, BCD digit                             |
| Byte               | 8 bits           | Smallest addressable data unit                   |
| Half-word          | 16 bits          | Definition of word is architecture-independent   |
| Word               | 32 bits          | A 32-bit architecture considers 1 word as 32-bit |
| Double Word        | 64 bits          |                                                  |
| Quad Word          |                  |                                                  |
Given a byte, bit 7 is the most significant bit (MSb) (small b for bit) ; bit 0 is least significant bit (LSb)

Bit = lowercase b ; byte = capital B
Computer architecture convention starts at 0

|  7  |  6  |  5  |  4  |  3  |  2  |  1  |  0  |
| :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: |
| MSb |     |     |     |     |     |     | LSb |
least significant and most significant can be extended to any binary data organization\

Given 12AB3456CAFE5678_base 16  
• What is the least significant bit? 
- 0
• What is the most significant bit?
- 0
• What is the least significant byte?
- 78
• What is the most significant byte?
- 12
• What is the least significant word?
- CAFE5678
• What is the most significant word?
- 12AB3456

### Byte Ordering System - Endianness

- refers to convention used to interpret the byte ordering of multi-byte stored in the computer memory
- Two types:
	- Big endian
	- Little Endian
- Coined by Danny Cohen based on his paper "On Holy Wars and a Plea for Peace"

#### Little Endian Byte Ordering System
- Multi-byte stores the least-significant byte at the lowest memory byte address followed by others in ascending order
- The address of the multi-byte is the address of the least significant byte.

| Address | Data (hex) |
| ------- | ---------- |
| 0003    | 55         |
| 0002    | 44         |
| 0001    | 33         |
| 0000    | 22         |
address 0000 contains the 16 bit data 33**22**
address 0000 contains the 32 bit data 554433**22**

#### Big Endian Byte Ordering System
- multi-byte stores MSB at lowest memory byte address followed by other bytes in ascending order of significance
- address of multi byte = address of most significant byte

| Address | Data (hex) |
| ------- | ---------- |
| 0003    | 55         |
| 0002    | 44         |
| 0001    | 33         |
| 0000    | 22         |
address 0000 contains 16 bit data **22**33
address 0000 contains 32 bit data **22**334455
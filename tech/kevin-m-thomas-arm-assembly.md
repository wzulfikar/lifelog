# Kevin M. Thomas - ARM Assembly
> Mon, 20 Mar 2017 at 13:11:52 MYT
https://www.linkedin.com/in/kevinmthomastr/recent-activity/posts/

This note contains points that I took when reading 40-series posts about ARM assembyl by Kevin M. Thomas.

Throughout the series, Kevil will use Raspberry Pi 3 which contains the Broadcom BCM2837 SoC with a 4x ARM Cortex-A53, 1.2GHz CPU and 1 GB LPDDR2 RAM. The OS used is Raspbian Jessie, Linux-based operating system. Read more about Raspberry PI here: [https://www.raspberrypi.org](https://www.raspberrypi.org)

---

- Keep in mind, 8 bits is equal to a byte and 2 nibbles are equal to a byte.

```
0101 = 5
1111 = f
→ 0101 1111 = 0x5f (0x prefix indicates hex)
```
- 1 nibble equals to 4 bits. 1 hex digit is 4 bits. Thus, each hex digit is a nibble in length. Therefore, two hex digits are a byte in length.

> Whether you are creating, debugging or hacking an Assembly, Python, Java, C, C++, R, JavaScript, or any other new language application that hits the street, ultimately everything MUST go down to binary 0 and 1 to which represent a +5V or 0V.

- ARM assembly utilizes the concet of two complements which inverts each bit and then finally adding 1: [https://www.linkedin.com/pulse/arm-assembly-part-4-binary-subtraction-kevin-m-thomas](https://www.linkedin.com/pulse/arm-assembly-part-4-binary-subtraction-kevin-m-thomas)
- 32-bits is actually 4 bytes of information which make up a word because 1 word equals to 4 bytes. Remember, 1 byte is 8 bits. Thus, 4 bytes is 32 bits (4 x 8 = 32)
- ARM microprocessor has internal storage which make any operation must faster as there is no external memory access needed
- The chip we are working with is known as a load and store machine. This means we load a register with the contents of a register or memory location and we can store a register with the contents of a memory or register location
- PC (Program Counter) is responsible for directing the CPU to what instruction will be executed next. The PC *literally* holds the address of the instruction to be fetched next
- You can refer PC to R15 as well when coding because register 15 is the program counter
- example of controlling PC directly in code:
`mov r15, 0x00000000`
- When hacking or reversing a binary, controlling the PC is essential to test for subroutine execution and learning about how the program flows in order to break it down and understand exactly what it is doing

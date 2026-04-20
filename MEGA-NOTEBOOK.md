# My Notebook: 16-bit Assembly from Zero

I wrote this while learning. No bullshit. Just what works.

---

## 16-bit Registers (Real Mode)

| Register | Name                    | What it does |
|----------|-------------------------|--------------|
| ax       | Accumulator             | Arithmetic, I/O |
| bx       | Base                    | Data pointer (index) |
| cx       | Counter                 | Loop counter |
| dx       | Data                    | Arithmetic, I/O ports |
| si       | Source Index            | Source for string copying |
| di       | Destination Index       | Destination for string copying |
| bp       | Base Pointer            | Stack pointer (function frame) |
| sp       | Stack Pointer           | Top of stack |
| ip       | Instruction Pointer     | Points to current instruction (can't change directly) |
| cs       | Code Segment            | Code segment |
| ds       | Data Segment            | Data segment |
| ss       | Stack Segment           | Stack segment |
| es       | Extra Segment           | Extra segment |
| fs       | Extra Segment 2         | Extra segment (32/64-bit) |
| gs       | Extra Segment 3         | Extra segment (32/64-bit) |
| flags    | Flags                   | Status flags (ZF, CF, OF, etc.) |

---

## When does a register (like bx) become a pointer?

**Only when you use it in square brackets:** `[bx]`

You can put anything in it. But with `[]` you activate its main function (like data pointer).

---

## BIOS Video Functions (int 0x10)

| AH     | What it does |
|--------|--------------|
| 0x00   | Set video mode |
| 0x01   | Set cursor shape |
| 0x02   | Set cursor position |
| 0x03   | Get cursor position |
| 0x06   | Scroll screen up |
| 0x07   | Scroll screen down |
| 0x0E   | **PRINT CHARACTER (teletype output)** |
| 0x0F   | Get current video mode |

---

## 32-bit Registers (Protected Mode)

| 32-bit | 16-bit | 8-bit (high) | 8-bit (low) |
|--------|--------|--------------|--------------|
| eax    | ax     | ah           | al |
| ebx    | bx     | bh           | bl |
| ecx    | cx     | ch           | cl |
| edx    | dx     | dh           | dl |
| esi    | si     | —            | — |
| edi    | di     | —            | — |
| ebp    | bp     | —            | — |
| esp    | sp     | —            | — |
| eip    | ip     | —            | — |
| eflags | flags  | —            | — |

---

## 64-bit Registers

| 64-bit | 32-bit (low) | 16-bit | 8-bit         |
|--------|--------------|--------|---------------|
| rax    | eax          | ax     | ah, al        |
| rbx    | ebx          | bx     | bh, bl        |
| rcx    | ecx          | cx     | ch, cl        |
| rdx    | edx          | dx     | dh, dl        |
| rsi    | esi          | si     | sil (low byte)|
| rdi    | edi          | di     | dil           |
| rbp    | ebp          | bp     | bpl           |
| rsp    | esp          | sp     | spl           |
| rip    | eip          | ip     | —             |
| rflags | eflags       | flags  | —             |

---

## Examples

| Register | Example              | What it does |
|----------|----------------------|--------------|
| ax       | `mov ax, 0x1234`     | Write number |
| al       | `mov al, 'A'`        | Write character |
| cx       | `loop .label`        | Decreases cx, jumps if not zero |
| dx       | `out 0x60, al`       | Send byte to keyboard port |

---

## Flags and Jump Instructions

| Instruction | Condition              | C equivalent |
|-------------|------------------------|--------------|
| jz          | ZF = 1 (result = 0)    | if (x == 0) |
| jnz         | ZF = 0 (result ≠ 0)    | if (x != 0) |
| je          | same as jz             | if (x == y) |
| jne         | same as jnz            | if (x != y) |
| jl          | less (signed)          | if (x < y) |
| jg          | greater (signed)       | if (x > y) |
| jb          | below (unsigned)       | if (x < y) |
| ja          | above (unsigned)       | if (x > y) |

---

## Flags

| Flag | Name             | When set |
|------|------------------|----------|
| ZF   | Zero Flag        | Result = 0 |
| CF   | Carry Flag       | Overflow on add/sub |
| SF   | Sign Flag        | Result is negative (high bit = 1) |
| OF   | Overflow Flag    | Signed overflow |
| DF   | Direction Flag   | String direction (0 = forward, 1 = backward) |
| IF   | Interrupt Flag   | Interrupts enabled (1) or disabled (0) |

---

## String Instructions

| Instruction | Reads from      | Writes to       | Updates |
|-------------|----------------|----------------|---------|
| lodsb       | `[ds:si]`       | al             | si |
| lodsw       | `[ds:si]`       | ax             | si |
| lodsd       | `[ds:si]`       | eax            | si |
| stosb       | al              | `[es:di]`      | di |
| stosw       | ax              | `[es:di]`      | di |
| stosd       | eax             | `[es:di]`      | di |
| movsb       | `[ds:si]`       | `[es:di]`      | si, di |
| movsw       | `[ds:si]`       | `[es:di]`      | si, di |
| movsd       | `[ds:si]`       | `[es:di]`      | si, di |
| scasb       | `[es:di]`       | compares with al | di |
| cmpsb       | `[ds:si]` & `[es:di]` | compares | si, di |

---

**Note:** `lodsb` uses `ds` (data segment) by default.  
`stosb` always uses `es` (extra segment).  
To read from a different segment — change `ds`.

---

## Example: Address Calculation

ds = 0x1000, si = 0x1234
Address = 0x10000 + 0x1234 = 0x11234

---

## I/O Ports

### Keyboard (PS/2)

| Port | Purpose          |
|------|------------------|
| 0x60 | Data (scan code) |
| 0x64 | Status / Command |

### Timer (PIT)

| Port | Purpose          |
|------|------------------|
| 0x40 | Channel 0 (counter) |
| 0x41 | Channel 1 |
| 0x42 | Channel 2 |
| 0x43 | Mode |

---

## Useful Instructions

| Instruction | Example          | What it does |
|-------------|------------------|--------------|
| add         | `add ax, bx`     | ax = ax + bx |
| sub         | `sub ax, 5`      | ax = ax - 5 |
| inc         | `inc cx`         | cx = cx + 1 |
| dec         | `dec si`         | si = si - 1 |
| mul         | `mul bx`         | dx:ax = ax * bx |
| div         | `div bx`         | ax = dx:ax / bx, dx = remainder |
| and         | `and al, 0x0F`   | Bitwise AND |
| or          | `or al, 0x30`    | Bitwise OR |
| xor         | `xor ax, ax`     | Zero out (faster than mov) |
| shl         | `shl ax, 2`      | Shift left (ax * 4) |
| shr         | `shr ax, 1`      | Shift right (ax / 2) |

---








































---

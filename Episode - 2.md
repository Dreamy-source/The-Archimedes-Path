### Episode 2

# Machine, brrzz.. wtf bro?!
- **WARNING**: I will not explain how to open a **text editor**, so we move on to studying.

## Registers [Boxes]
-  **Register** is just a **box**. You put numbers — or whatever you need — **into it**.
- `mov ax, 5` — put number 5 into box `ax`
- `add ax, 3` — adding stupid number 3 into box `ax` and getting number 8 in `ax`
- **Box** `ax` changes the **number** in it immediately to **8** when we add a new number, **nothing difficult**
- That's it. **No magic.**
- **Boxes** have names: `ax`, `bx`, `cx`, `dx`, `si`, `di`, `bp`, `sp`
- Each box holds numbers from **0 to 65535** (that's 16 bits)
- **NOTE**: This is just - **A**, **B**, **C**, **D** and others.
- - **Example**: **A** - adding **a** to **x** and getting **register** [ax], **B** - adding **b** to **x** and getting **register** [bx], **C** - adding **c** to **x** and getting **register** [cx], **D** - adding **d** to **x** and getting **register** [dx].

# Instructions [this is not hard, bro]
```markdown
- add - Add. Just add.
- add example:
```
```asm
mov ax, 5   ; ax = 5
add ax, 3   ; adding number 3 to ax
; Result: 8
```
---
```markdown
- **sub** - Sub. Just sub. Just **subtract**.
- **sub example**:
```
```asm
mov ax, 5   ; ax = 5
sub ax, 2   ; subtract 2 from ax
; Result: 8
```
---
 
  # Comming to Episode - 3!
  - Here is **URL** to next episode: https://github.com/Dreamy-source/ASM-for-Humans/blob/main/Episode%20-%203.md

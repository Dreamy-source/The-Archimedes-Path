### Episode 3 🚀

## Inc, Dec [+1] or [-1]
-  **✅ Inc** is just a **+1** number. Economy and **fast!** [1 Byte] 🧊.
- ```asm
  mov ax, 5   ; [📦] ax = 5
  inc ax      ; [📦] ax = 6  [1 Byte]
  
  ; Just increase on 1 ⭐
  ; Result: 6 ✅
  ```
---
-  **✅ Dec** is just a **-1** number. Economy and **fast**! [1 - 2 Byte] 🧊.
- ```asm
  mov ax, 5   ; [📦] ax = 5
  dec ax      ; [📦] ax = 4  [1 Byte]
  
  ; Just decrease on 1 ⭐
  ; Result: 4 ✅
  ```
  
## Bad examples
-  **⚠️ Bad example [Add]**:
- ```asm
  mov ax, 5   ; [📦] ax = 5
  add ax, 1   ; [📦] ax = 4  [3 - 4 Byte] ❗
  
  ; 
  ; Result: 6, but i lost 3 - 4 bytes ❌
  ; Why? Because if you need increase number to 1, do inc ✅
---
-  **⚠️ Bad example [Sub]**:
- ```asm
  mov ax, 5   ; [📦] ax = 5
  sub ax, 1   ; [📦] ax = 4  [3 - 4 Byte] ❗
  
  ; 
  ; Result: 4, but i lost 3 - 4 bytes ❌
  ; Why? Because if you need decrease number to 1, do dec ✅
  
# 📦 Instructions [This is not hard]
## 🔧 ADD
```asm
; add example:

mov ax, 5   ; [📦] ax = 5
add ax, 3   ; adding number 3 to ax

; Result: 8 ✅
```
---
## 🔧 SUB
```asm
; sub example:

mov ax, 5   ; [📦] ax = 5
sub ax, 2   ; subtract 2 from ax

; Result: 3 ✅
```
---
## 🔧 INC
```asm
; inc example:

mov ax, 5   ; [📦] ax = 5
inc ax      ; [📦] ax = 6  [1 Byte]
  
; Just increase on 1 ⭐
; Result: 6 ✅
```
---

## 🔧 DEC
```asm
; dec example:

mov ax, 5   ; [📦] ax = 5
dec ax      ; [📦] ax = 4  [1 Byte]
  
; Just decrease on 1 ⭐
; Result: 4 ✅
```
---

# Comming to Episode - 4! 🔥
 - Here is **URL** to next episode: https://github.com/Dreamy-source/ASM-for-Humans/blob/main/Episode%20-%203.md

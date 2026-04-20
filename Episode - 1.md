### Episode 1

# Development environment

- **NASM** — because we write **real assembly**, not that fake stuff.
- **QEMU** — so you **don't kill your computer** (but if you want to live dangerously — a **USB** stick works too).
- **Text Editor** — Notepad, NANO, NP++, Notebook, VS Code or any other text editor.
- **Brain** — the most important tool. Must be turned **on**.

## What you need to know before Episode 1:
- How to open terminal/command prompt
- How to install programs on your OS
- That's it. **Really**.
- **NOTE:** All commands for running/compiling will be according to the book further

## Instalation
- ## Linux
  - ### Pacman
    - **Arch Linux**
    - **Manjaro**
    - **EndeavourOS**
    - **Garuda Linux**
    - **ArcoLinux**
    - **CachyOS**
    - **Artix Linux**
      ```bash
      echo "Note for pacman users: qemu-full installs everything (all architectures`). If you want only x86_64, use qemu-system-x86_64. But we like full — just in case you want to emulate a           toaster later."
      ```
      ```bash
      echo 'Installing: NASM, QEMU'
      sudo pacman -S nasm qemu-full
      ```
  - ### Apt
    - **Debian**
    - **Ubuntu**
    - **Linux Mint**
    - **Kali Linux**
    - **Zorin OS**
    - **Elementary OS**
    - **Raspberry Pi OS**
      ```bash
      echo 'Installing: NASM, QEMU'
      sudo apt install nasm qemu-system-x86-64
      ```
- ## Windows
- Download **NASM** from https://nasm.us
  
- Download **QEMU** from https://qemu.org

- In installation guide, press "Add to path" button.

- After installation, open **Command Prompt** and type:
  ```cmd
  nasm -v
  qemu-system-x86_64 -version
  ```
- If commands has been completed successfully, with pointers on version of **NASM** and **QEMU** — then go to next.

# Comming to Episode - 2!
- Here is **URL** to next episode: https://github.com/Dreamy-source/ASM-for-Humans/blob/main/Episode%20-%202.md

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
    - **NOTE**: for pacman users: **qemu-full** installs **everything** (all architectures`). If you want only **x86_64**, use **qemu-system-x86_64**. But we like **full** — just in case you want to emulate a **toaster** later.
    ---
      ```bash
      echo "Note for pacman users: qemu-full installs everything (all architectures`). If you want only x86_64, use qemu-system-x86_64. But we like full — just in case you want to emulate a toaster later."
      ```
    ---
      ```bash
      echo 'Installing: NASM, QEMU'
      echo 'Press CTRL + C, if you need to leave from downloading.'
      sudo pacman -S nasm qemu-full
      echo 'Downloading completed, or interrupted by user.'
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
      echo 'Press CTRL + C, if you need to leave from downloading.'
      sudo apt install nasm qemu-system-x86-64
      echo 'Downloading completed, or interrupted by user.'
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
- ## MacOS
  - Install **Homebrew** first (https://brew.sh)
  - Then:
    ```bash
    brew install nasm qemu
    ```
- If commands has been completed successfully, with pointers on version of **NASM** and **QEMU** — then go to next.

# Comming to Episode - 2!
- Here is **URL** to next episode: https://github.com/Dreamy-source/ASM-for-Humans/blob/main/Episode%20-%202.md

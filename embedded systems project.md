
# 📘 Embedded Systems Introduction

## 1. What is an Embedded System?

An **Embedded System** is a combination of computer **hardware** and **software** designed to perform a **specific function** or set of functions.

### 🔑 Key Characteristics
- Contains a **processing unit**
- Includes **temporary memory** (RAM) and **permanent storage** (Flash, ROM)
- **Customized** for specific applications
- **Low cost** compared to general-purpose computers

---

## 2. 📱 Real-life Example: Smartphone

A smartphone is a complex system with multiple embedded components.  
Each component can be considered an embedded system in itself.

---

## 3. 🔐 Software Perspective: Security System Example

### Option 1: General-Purpose Computer
- Attach a camera and develop an intruder detection app.
- ✅ Pros: Easy and fast to develop  
- ❌ Cons: Expensive (~₹100,000 PC + ₹3,500 camera), overkill features (display, keyboard, etc.)

### Option 2: Raspberry Pi (General-Purpose Embedded Board)
- Attach a camera and write custom software  
- 💰 Cost: ₹4,000 (RPi) + ₹3,500 (camera) + ₹1,000 (Wi-Fi) ≈ ₹6,500  
- ❌ Still not optimal: Unused hardware like HDMI, USB, Ethernet

### Option 3: Custom Embedded System
- Based on Raspberry Pi design
- Hardware engineer builds a custom PCB with only essential components
- Software engineers write software to handle alert functionality
- 💰 Cost: ₹1,000 (custom board) + ₹3,500 (camera)

---

## 4. 📍 Where Are Embedded Systems Found?
- TVs  
- Home Appliances  
- Gaming Consoles  
- Automobiles  
- Medical Devices  
- Industrial Robots

---

## 5. ✅ Advantages and ❌ Disadvantages

**Pros:**
- Cost-efficient
- Purpose-built for specific tasks
- Optimized performance and user experience

**Cons:**
- Hardware constraints (limited RAM, CPU, I/O)
- Longer development time compared to PCs

---

## 6. 🖥️ Desktop Linux vs ⚙️ Embedded Linux

### Desktop Linux
- Runs on **general-purpose hardware** (laptops, desktops)
- Uses **ready-made boards** (Intel, AMD PCs)
- Focus: **software customization**
- Features: full GUIs (GNOME, KDE), broad hardware support

💡 **Key Point**: You don’t change the hardware — you just install/remove software

### Embedded Linux
- Runs on **custom-designed hardware** (like Raspberry Pi)
- Focus: **hardware customization** (CPU, RAM, I/O)
- Features: no desktop, minimal services/libraries, CLI or lightweight GUI

💡 **Key Point**: You design the hardware and create a matching OS

---

## 7. 🧱 Embedded Linux Architecture

### Bootloader
- Initializes CPU, RAM, Memory, and loads Linux Kernel  
- **Primary Bootloader** → **Secondary Bootloader** → Load Kernel

### Device Tree
- Hierarchical description of hardware (CPU, buses, peripherals)

### Linux Kernel Image: Responsibilities
- Network Stack (TCP/IP, Wi-Fi)
- Virtual File System (VFS)
- Process & Memory Management (MMU)
- IPC (Inter-Process Communication)
- Device Drivers (USB, SPI, etc.)
- System Call Interface

### Root File System (RootFS)
- Directories: `/bin`, `/lib`, `/etc`, etc.
- Contains: BusyBox, libraries, configs
- **BusyBox**: compact command-line tools suite

### Firmware
- Software flashed to device (bootloader + kernel + rootfs)

---

## 8. 🧰 Toolchain (Compiler + Tools)

### What is a Toolchain?
- A toolset for **cross-compiling** (host → embedded target)

### Common Tools:
| Tool     | Purpose                                      |
|----------|----------------------------------------------|
| gcc      | Compile C/C++ to machine code                |
| linker   | Combine object files into a program          |
| gdb      | Debugging tool to identify and fix errors    |

---

## 9. 🧪 What is Yocto?

Yocto is a **build system** used to create custom Linux distributions.

### What is a Linux Distribution?
- Composed of user space (apps/utilities) and kernel space (hardware, drivers)
- Linux OS = Linux Kernel + utilities + bootloader + drivers

---

## 10. 🚀 Why Use Yocto?

- **Highly Customizable** (choose drivers, libraries)
- **Industry-grade Toolchain**
- **Layer-based workflow** (modular + reusable)

### Yocto Workflow Overview:

1. **Source Code** – Raw code: app, kernel, bootloader, configs  
2. **Build System** – Central logic using **BitBake**  
   - BitBake reads recipes & runs steps (fetch → compile → install)  
   - Uses a toolchain for cross-compilation  
3. **OpenEmbedded** – Metadata/layers for build instructions  
4. **Output Folder** – Contains compiled binaries (e.g., `zImage`, `rootfs.ext4`, `u-boot.bin`)  
5. **System Image** – Final `.img` or `.wic` image for flashing  
6. **Terminal** – Interface for commands, logs, and debugging

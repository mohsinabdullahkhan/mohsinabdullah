# mohsinabdullah


An educational operating system kernel project designed to demonstrate
kernel architecture, multitasking, memory management, interrupts,
system calls, and basic OS services.

The project is divided into **10 independent kernel modules**. Each module
will initially be developed separately and will later be integrated into
the complete kernel.

---

## Project Objectives

The main objectives of this project are:

- Understand basic operating-system kernel architecture
- Implement fundamental kernel services
- Develop a multitasking environment
- Understand CPU scheduling and context switching
- Manage memory inside the kernel
- Handle hardware and software interrupts
- Provide system calls to user programs
- Implement basic inter-process communication
- Provide a simple filesystem
- Develop a kernel command shell

---

# Kernel Modules

## 1. Boot & Kernel Initialization

**Purpose:**  
Responsible for starting the kernel and performing the initial system
configuration.

### Responsibilities

- Kernel entry point
- CPU initialization
- Kernel initialization
- Initialize global kernel structures
- Initialize other kernel modules
- Transfer control to the main kernel

### Planned Functions

```text
kernel_init()
cpu_init()
kernel_main()

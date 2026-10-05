# mohsinabdullah

An extension of the MIT xv6 teaching operating system (RISC-V) with 10 new kernel modules:
5 OS-level modules (multitasking) and 5 architecture-level modules (RISC-V).

**Author:** [Your Name] (individual project)
**Course:** [Course Name / Code]
**Instructor:** [Teacher Name]
**Base repository:** https://github.com/mit-pdos/xv6-riscv

---

## Modules

### Part 1: OS modules (multitasking)

| # | Module | Subsystem | Syscalls | Test program | Status |
|---|--------|-----------|----------|--------------|--------|
| 1 | Lseek | File offsets | `lseek()` | `lseektest` | Planned |
| 2 | User-Level Threads | Context switching in user space | `thread_create()`, `thread_yield()`, `thread_schedule()` | `uthread` | Planned |
| 3 | Environment Variables | Per-process data (inherited by fork/exec) | `setenv()`, `getenv()` | `envtest` | Planned |
| 4 | Buffer Cache Statistics | Disk block cache (`bio.c`) | `bcachestat()` | `bcachestat` | Planned |
| 5 | Rename | Directory entries and inodes | `rename()` | `renametest` | Planned |

### Part 2: Architecture modules (RISC-V)

| # | Module | Subsystem | Syscalls / interface | Test program | Status |
|---|--------|-----------|----------------------|--------------|--------|
| 6 | WFI Idle Loop and Idle Stats | CPU power state (`wfi`) | `idlestat()` | `idletest` | Planned |
| 7 | Register Dump | Trapframe (general-purpose registers) | `regdump()` | `regdump` | Planned |
| 8 | UART Statistics | Serial driver (`uart.c`) | `uartstat()` | `uartstat` | Planned |
| 9 | Stack Watermark | User stack and guard page | `stackinfo()` | `stacktest` | Planned |
| 10 | PLIC Interrupt Info | Platform-level interrupt controller | `plicinfo()` | `plicinfo` | Planned |

Detailed documentation for each module is in the [`docs/`](docs/) folder.

---

## Prerequisites

- RISC-V GNU toolchain (`riscv64-linux-gnu-gcc` or `riscv64-unknown-elf-gcc`)
- QEMU with `riscv64-softmmu` (`qemu-system-riscv64`)
- Linux, macOS, or WSL2 on Windows

Ubuntu / WSL:

```bash
sudo apt install git build-essential gdb-multiarch qemu-system-misc \
     gcc-riscv64-linux-gnu binutils-riscv64-linux-gnu
```

## Build and Run

```bash
git clone https://github.com/<your-username>/<your-repo-name>.git
cd <your-repo-name>
make qemu
```

Exit QEMU with `Ctrl-A` then `X`.

## Usage Examples

Filled in as each module is completed:

```text
$ lseektest
$ uthread
$ envtest
$ bcachestat
$ renametest
$ idletest
$ regdump
$ uartstat
$ stacktest
$ plicinfo
```

## Repository Structure

```text
kernel/    modified and new kernel source files
user/      user-space test programs
docs/      one documentation file per module
mkfs/      xv6 filesystem image builder (unchanged)
Makefile   build rules (UPROGS extended with the new programs)
```

## Design Notes and Limitations

To be added per module.

## Credits

Based on xv6-riscv by MIT PDOS (https://github.com/mit-pdos/xv6-riscv), a
re-implementation of Dennis Ritchie's and Ken Thompson's Unix Version 6 for RISC-V.
xv6 is inspired by John Lions's *Commentary on UNIX 6th Edition*. See the original
`README` file in this repository for the full list of xv6 contributors.

# Hello Kernel Module (Simple Guide)

## What is this?

This is a **simple Linux Kernel Module (Hello World)**.

* It runs inside the **Linux kernel**
* It prints a message when loaded and removed
* It is **NOT** a normal C program

---

## Requirements (Run once)

```bash
sudo apt update
sudo apt install build-essential linux-headers-$(uname -r)
```

Verify headers:

```bash
ls /lib/modules/$(uname -r)/build
```

---

## Files

```text
hello_kernel/
├── hello.c
├── Makefile
└── README.md
```

---

## How to Run (Step by Step)

### 1. Go to project folder

```bash
cd ~/hello_kernel
```

---

### 2. Compile the kernel module

```bash
make
```

After success, you will see:

```text
hello.ko
```

---

### 3. Load (run) the module

```bash
sudo insmod hello.ko
```

(No output is normal)

---

### 4. Check output message

```bash
dmesg | tail
```

You will see:

```text
Hello, Kernel! Module Loaded.
```

---

### 5. Remove the module

```bash
sudo rmmod hello
```

---

### 6. Check removal message

```bash
dmesg | tail
```

You will see:

```text
Goodbye, Kernel! Module Unloaded.
```

---

## Important Notes

* Do NOT use `gcc`
* Do NOT run `./hello`
* Always use `make`
* Use `dmesg` to see output
* Run on **Ubuntu VM / Dual Boot**, not WSL

---

## Author

Rushil Kevadiya

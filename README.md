# 🔐 8086 Assembly Secure Room Access System

## 📌 Overview
This project implements a **Secure Room Access System** using **8086 Assembly Language**, developed for the **Computer Organization and Assembly Language (ENCS336)** course. It simulates a secure lock system for a company with 10 employees, each identified by a **16-bit Employee ID** and an **8-bit Password**.

Employees can access the secure room only after successful **authentication**.

---

## 👤 Employee Authentication Process

Each employee must enter:
- `Employee ID` (16-bit)
- `Password` (8-bit)

After input, the system:
- Encrypts the input password using a specific scheme
- Validates the ID and encrypted password against stored records
- Displays:  
  - ✅ **Access Allowed** – if credentials match  
  - ❌ **Access Denied** – otherwise

---

## 🔒 Password Encryption Scheme

Passwords are stored in memory in encrypted form. The encryption works as follows:

- If the **MSB (Most Significant Bit)** ≠ **LSB (Least Significant Bit)**:
  - Swap the MSB and LSB
- If the **MSB == LSB**:
  - Rotate the password right by **2 bits**

This ensures passwords are securely stored and verified using the same runtime transformation.

---

## 🛠️ How the Program Works

The 8086 assembly code performs the following steps:

1. **Initialization**:
   - Loads 10 predefined employee IDs and their encrypted passwords into memory.

2. **User Input**:
   - Takes ID and password input via keyboard.
   - Password entry uses `INT 21h, Function 08h` (no character echo).

3. **Encryption**:
   - Applies the MSB-LSB based encryption algorithm to the input password.

4. **Validation**:
   - Searches for the entered ID in memory.
   - Compares encrypted password against the stored encrypted password.

5. **Result Display**:
   - Shows either `Access Allowed` or `Access Denied`.

---

## 💾 Sample Employee Data

| Employee ID | Original Password |
|-------------|-------------------|
| 65          | 125               |
| 148         | 84                |
| 526         | 29                |
| 2036        | 37                |
| 1504        | 187               |
| 82          | 219               |
| 112         | 62                |
| 2840        | 75                |
| 940         | 141               |
| 1292        | 243               |

> These passwords are encrypted using the scheme before being stored in memory.

---

## 📂 Project Files

- `CODE_ASM.asm` – Complete 8086 Assembly source code.
- `Assembly_Project.pdf` – Project assignment and requirements.
- `Project_Report.pdf` – Documentation with solution explanation and screenshots.

---

## 📚 Acknowledgments

This project was created as part of:

**ENCS336 – Computer Organization and Assembly Language**  
Semester: **Fall 2024/2025**

Team Members:  
- 👤 *Anas AL Sayed*  
- 👤 *ABD AL-RHEEM YASEEN*  
- 🎓 Birzeit University

---


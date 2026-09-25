# Week 3 – PDF Password Recovery using John the Ripper

## 📌 Overview

This lab was completed as part of the **NetworkWalks Cybersecurity Training – Week 3**.

The objective of this task was to understand how password-protected PDF files can be analyzed and how password recovery can be performed using **John the Ripper (JTR)** and the **NetworkWalks Hash Calculator and Password Cracker** tools.

---

## 🎯 Objectives

- Understand how password-protected PDF files are handled.
- Extract a crackable password hash from a PDF.
- Use **John the Ripper (JTR)** to perform dictionary-based password recovery.
- Use the **NetworkWalks Hash Calculator** to generate PDF hashes.
- Use the **NetworkWalks Password Cracker** to recover passwords.
- Verify the recovered passwords by opening the protected PDF files.

---

## 🛠️ Tools Used

- **Kali Linux**
- **John the Ripper (JTR)**
- **pdf2john**
- **NetworkWalks Hash Calculator**
- **NetworkWalks Password Cracker**
- Password-protected PDF files

---

# 🔹 Task 1 – John the Ripper

### Step 1: Extract the PDF Hash

The `pdf2john` utility was used to extract the password hash from the protected PDF.

```bash
pdf2john "/home/kali/Downloads/My Locked PDF1.pdf"
```

The extracted hash was then saved to a file:

```bash
pdf2john "/home/kali/Downloads/My Locked PDF1.pdf" > pdf_hash.txt
```

The hash file was verified using:

```bash
cat pdf_hash.txt
```

### Step 2: Run John the Ripper

John the Ripper was executed against the extracted hash:

```bash
john pdf_hash.txt
```

JTR successfully recovered the password.

### Step 3: Verify the Recovered Password

The result was displayed using:

```bash
john --show --format=PDF pdf_hash.txt
```

The recovered password was then used to open the protected PDF successfully.

### 📸 Evidence

![PDF 1 Hash Extraction](01_JTR_PDF1_Hash_Extraction.png)

![PDF 1 Password Cracked](02_JTR_PDF1_Password_Cracked.png)

![PDF 1 Unlocked](04_JTR_PDF1_Unlocked.png)

---

# 🔹 Task 2 – NetworkWalks Hash Calculator

For the second PDF, the **NetworkWalks Hash Calculator** was used.

### Steps

1. Opened the NetworkWalks Hash Calculator.
2. Uploaded the password-protected PDF.
3. Generated the PDF password hash.
4. Recorded the generated hash for the next step.

### 📸 Evidence

![PDF 2 Hash Calculator](05_PDF2_Hash_Calculator.png)

---

# 🔹 Task 3 – NetworkWalks Password Cracker

The generated PDF hash was entered into the **NetworkWalks Password Cracker**.

### Steps

1. Opened the NetworkWalks Password Cracker.
2. Pasted the generated PDF hash.
3. Started the password recovery process.
4. Successfully obtained the PDF password.
5. Used the recovered password to open the protected PDF.

### 📸 Evidence

![PDF 2 Password Cracked](06_PDF2_Password_Cracked.png)

![PDF 2 Unlocked](07_PDF2_Unlocked.png)

---

# 🔹 Task 4 – Third PDF

The same workflow was performed on the third password-protected PDF.

### Steps

1. Uploaded the PDF to the NetworkWalks Hash Calculator.
2. Generated the PDF hash.
3. Copied the hash into the NetworkWalks Password Cracker.
4. Started the password recovery process.
5. Obtained the password.
6. Used the password to successfully open the PDF.

### 📸 Evidence

![PDF 3 Hash Calculator](08_PDF3_Hash_Calculator.png)

![PDF 3 Password Cracked](09_PDF3_Password_Cracked.png)

![PDF 3 Unlocked](10_PDF3_Unlocked.png)

---

# 🧠 What I Learned

Through this lab, I learned:

- How password-protected PDF files can be converted into a format that password-recovery tools can process.
- How `pdf2john` is used to extract PDF password hashes.
- How John the Ripper can perform dictionary-based password recovery.
- How to save command output into a file using `>`.
- How to verify a recovered password using JTR's `--show` option.
- How hash extraction and password recovery can also be performed using web-based lab tools.
- The importance of verifying a recovered password by successfully opening the protected PDF files.

---

# ⚠️ Lab Scope

All activities in this repository were performed on password-protected PDF files provided for the **NetworkWalks cybersecurity training lab** and were conducted for educational purposes.

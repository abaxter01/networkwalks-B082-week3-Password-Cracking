# Week 3: Password Cracking with Jack The Ripper and Networkwalks Tools

## 📌 Introduction

Password security is one of the most important areas of cybersecurity. Weak or commonly used passwords can place personal files, accounts, and organizational systems at risk. Password cracking is therefore used by authorized security professionals to test password strength and demonstrate the importance of strong password protection.

This project was completed as part of my **Week 3 Cybersecurity & Ethical Hacking training with Networkwalks**. The objective was to understand the basic password recovery process by working with a *password-protected PDF* file in an authorized lab environment.

Two approaches were explored:

1. John the Ripper (JTR) and Johnny GUI
2. Networkwalks Hash Calculator and Password Cracker

<br>

> **⚠️ Ethical Use Notice:** This walkthrough is intended strictly for educational purposes and authorized security testing. Password recovery tools should only be used on files, accounts, and systems that you own or where you have explicit permission to perform testing. This repository does not encourage unauthorized access to another person's files, accounts, devices, or systems.

--- 
## 🧠 Key Concepts

It is important to understand several basic key cybersecurity concepts before attempting this exercise:

<br>

**1. What is a Password?**

A **password** is a secret value used to authenticate a user and help protect access to a system, account, or file.

Strong passwords are important because weak or predictable passwords may be easier to guess or recover during an authorized password-security assessment.

*OWASP recommends protecting stored passwords with modern password-hashing methods rather than storing them in plain text.*

<br>

**2. What is Hashing?**

**Hashing** is the process of applying a mathematical algorithm to data to produce a fixed or representative value known as a *hash* or *hash digest*.

A cryptographic hash function is designed so that recovering the original input from the hash is computationally difficult. NIST describes hashing as producing a value representative of the original data and identifies important cryptographic properties such as one-way operation and collision resistance.

- **Simple Example**

Password ➔ Hash Function ➔ Hash Value

In password security, a system can compare a newly generated hash with a stored hash rather than storing the original password directly.

<br>

**3. What is a Hash?**

A **hash** is the output generated when data is processed by a hash function.

In this lab, the password-protected PDF 'My Locekd PDF1' was processed to obtain a hash value that began with:

`$pdf$...`

The complete hash was required for the password recovery process. 

> **To Note:** A hash is not simply the original password written in another format. Password cracking generally involves testing candidate passwords and comparing their resulting values with the target information.

<br>

**4. What is Encryption?**

**Encryption** is a process used to protect information by converting readable data into a protected form that can be returned to readable form using the appropriate key.

A simple representation is:

Readable Data ➔ Encryption ➔ Protected Data ➔ Decryption Key ➔ Readable Data

Networkwalks training material describes encryption as a two-way function, while hashing is described as a one-way function.

OWASP similarly distinguishes encryption from hashing: encrypted data is intended to be recoverable with the appropriate key, while hashing is generally used for one-way password verification.

<br>

**6. What is Password Cracking?**

**Password cracking** is the process of attempting to recover or identify a password from protected data or password-related information.

In an authorized security assessment, password cracking can be used to:

- Test password strength
- Identify weak passwords
- Demonstrate password-related security risks
-Improve organizational password policies

The Networkwalks Week 3 lab explains password cracking as recovering a password from stored data or a protected file to demonstrate the risks associated with weak passwords.

---
## 🛠️ Tools Used

#### 1. John the Ripper (JTR)

John the Ripper, commonly called JTR, is a password-cracking tool used to test password strength and recover supported password formats during authorized security testing.

According to the official Openwall documentation, John the Ripper supports multiple operating systems (Unix, Windows, Linux, and Mac) and numerous password hash types.

- **Johnny**

Johnny is the graphical user interface (GUI) version used in the training exercise.

#### 2. Networkwalks Hash Calculator

The Networkwalks Hash Calculator was used in the second practical exercise to extract the relevant hash information from the password-protected PDF file.

    https://networkwalks.com/hash-calculator/

#### 3. Networkwalks Password Cracker

The Networkwalks Password Cracker was then used to process the extracted hash and attempt password recovery.

    https://networkwalks.com/password-cracker/

---
## 🧪 Lab 1: Password Cracking with John the Ripper and Johnny

#### 🎯 Objective

The objective of this lab was to recover the password of the authorized, password-protected PDF file provided for the training exercise.

The practical used:

- John the Ripper
- Johnny GUI
- A password-protected PDF 'My LockedPDF1'
- Extracted PDF hash information 'hash_lockedpdf1.txt'

---

### Step 1a: Install John the Ripper

Download and install John the Ripper on the Windows computer.

The Networkwalks lab provides the official Openwall website as a source for John the Ripper.

    https://www.openwall.com/john/

<img width="1363" height="669" alt="Screenshot 2026-08-27 213134__x2" src="https://github.com/user-attachments/assets/86de99a8-2df3-4aad-a5fe-2dae6a9f9a4c" />

### Step 1b: Install Johnny

Download Johnny GUI from official website

    https://openwall.info/wiki/john/johnny

<img width="1141" height="404" alt="image" src="https://github.com/user-attachments/assets/c7313c48-8023-4fc5-b9d0-25707bd965ea" />


### Step 2: Install and Configure Johnny

After installing Johnny, open the application and configure it to locate the appropriate John executable.

The lab instructions require selecting the `john.exe` file from the appropriate installation directory.

<img width="935" height="429" alt="image" src="https://github.com/user-attachments/assets/d52fbacd-ae2f-4d21-b6e2-6bab1f210f2f" />

### Step 3: Obtain the PDF Hash

The next step was to work with the password-protected PDF file **My Locked PDF1** and obtain the hash information required by the password recovery tool.

Open the hash website (https://www.onlinehashcrack.com/tools-pdf-hash-extractor.php) and upload your pdf file to find its hash.

<img width="894" height="411" alt="image" src="https://github.com/user-attachments/assets/6bf819b5-a04f-4189-80d5-300c4618f302" />

<br> 

> ⚠️ Do not publicly upload sensitive or confidential documents to third-party services. This lab should only use the authorized training file provided for the exercise.

### Step 4: Save the Hash to a Text File

The extracted hash was copied into a text file.

For this lab, the file was saved as:

`hash_lockedpdf1.txt`

*The hash needed to remain complete and properly formatted before being loaded into Johnny.*

<img width="498" height="107" alt="image" src="https://github.com/user-attachments/assets/01fecea7-3147-4cd6-a830-91b433c4524a" />

### Step 5: Load the Hash File into Johnny

Johnny was opened and the password file option was used to browse for and select the saved hash file.

<img width="992" height="714" alt="image" src="https://github.com/user-attachments/assets/bfc58aa0-20d2-4e4e-afb8-8f9833e64cbb" />

### Step 6: Start the Password Recovery Process

After loading the hash file, start the password recovery process through the Johnny interface.

The amount of time required may depend on factors such as password complexity and computer performance.

<img width="1007" height="710" alt="image" src="https://github.com/user-attachments/assets/ca7bb81f-f68e-4cac-b994-df23a3bbc20a" />

### Step 7: Verify the Result

After the password was recovered in the authorized lab environment, it was used to open the protected PDF file.

<img width="1077" height="639" alt="image" src="https://github.com/user-attachments/assets/14b0ae03-615d-49dd-86e1-c8d7ad0063da" />

---
## 🧪🧪 Lab 2: Password Cracking with Networkwalks Tools

#### 🎯 Objective

The second exercise used two browser-based tools created by Networkwalks:

1. Networkwalks Hash Calculator
2. Networkwalks Password Cracker

This approach demonstrated the same general password recovery concept using a web-based workflow rather than the JTR/Johnny application workflow.

---
### Step 1: Open the Hash Calculator

Open the Networkwalks Hash Calculator in a web browser.

        https://networkwalks.com/hash-calculator/

Upload the locked PDF file **My LockedPDF1** to the Hash Calculator. The tool is used to process the protected PDF and obtain the relevant hash information.

<img width="1176" height="673" alt="image" src="https://github.com/user-attachments/assets/195941d0-1347-4488-8a22-4a384317f5a8" />

### Step 2: Copy the Complete Hash

Copy the entire hash value produced by the tool.

No portion of the hash should be omitted.

### Step 3: Open the Networkwalks Password Cracker

Open the Networkwalks Password Cracker in a web browser.

        https://networkwalks.com/password-cracker/

<img width="1161" height="618" alt="image" src="https://github.com/user-attachments/assets/a284f2f4-bf7f-4465-a521-f49d4b28dc67" />

### Step 6: Submit the Hash

Paste the extracted hash into the Password Cracker and begin the password recovery process.




---
## 👤 Author
**Anieka Baxter**

Cybersecurity Professional B082 Intern

LinkedIn: www.linkedin.com/in/anieka-baxter-b6156618b

---
### 📚 Program Information
**Program Name:** Cybersecurity at Networkwalks 

**Week:** 03 | **Project:** Password Cracking | **Repository:** GitHub

# networkwalks-week3-password-cracking

# Week 3 – Project Module 2: Password Cracking with Networkwalks Tools

## Overview
This project demonstrates how password-protected files store credentials as cryptographic hashes and how dictionary attacks can be used to recover weak or common passwords. Using the browser-based **Networkwalks Hash Calculator** and **Password Cracker** tools, I extracted a crackable hash from an encrypted PDF (`My Locked PDF1.pdf`) and recovered the password to capture the lab flag.

---

## Tools Used
* **Networkwalks Hash Calculator:** Extracted a `pdf2john` / `hashcat`-compatible `$pdf$` hash from the locked PDF.
* **Networkwalks Password Cracker:** Performed an automated dictionary attack against the extracted hash.
* **Custom Wordlists:** Scaled beyond the default 100-word list using a larger `.txt` wordlist to find the matching password.

---

## Step-by-Step Methodology

### 1. Hash Extraction
* Opened the **PDF** tab in the Networkwalks Hash Calculator and uploaded `My Locked PDF1.pdf`.
* Extracted the `$pdf$` hash string representing the file's encrypted password.

### 2. Dictionary Attack
* Pasted the extracted `$pdf$` hash into the Networkwalks Password Cracker.
* Tested the default 100-password list first, then uploaded a larger `.txt` wordlist when the initial list returned no match.
* Successfully matched the hash and recovered the plaintext password.

### 3. File Decryption & Flag Capture
* Opened `My Locked PDF1.pdf` and entered the cracked password to unlock the document and capture the **1st Flag**.

---

## Key Security Takeaways
* **Encryption vs. Hashing:** Encryption is a two-way process that can be reversed with the proper key, whereas hashing is a one-way function that produces a unique message digest.
* **Defense Against Dictionary Attacks:** Short, common, or leaked passwords can be cracked rapidly using automated wordlists. Enforcing long, complex, and unique passwords significantly increases resistance against offline cracking attacks.

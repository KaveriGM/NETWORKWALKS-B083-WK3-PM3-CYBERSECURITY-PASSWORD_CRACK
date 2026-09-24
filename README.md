# NETWORKWALKS-B083-WK3-PM3-CYBERSECURITY-PASSWORD_CRACK

## Encrypted PDF Password Recovery Using John the Ripper and NetworkWalks

A hands-on cybersecurity lab focused on understanding password recovery techniques for encrypted PDF files using **John the Ripper** and the **NetworkWalks Password Cracking Tool** in an authorized training environment.

---

## Objective

The objective of this lab was to understand the process of recovering passwords from encrypted files/PDFs and to gain practical experience with different password-recovery tools.

The exercise involved two approaches:

1. **John the Ripper (JtR)** – performing local password recovery using extracted PDF password hashes and wordlists.
2. **NetworkWalks Password Cracking Tool** – exploring an alternative password-recovery workflow to understand how other security tools perform password testing beyond John the Ripper.

This exercise also helped demonstrate the importance of password complexity, password strength, and secure password management.

---

## Tools & Technologies

| Tool / Technology | Purpose |
|---|---|
| **Kali Linux** | Cybersecurity testing and lab environment |
| **John the Ripper** | Offline password recovery |
| **NetworkWalks Password Cracking Tool** | Alternative password-recovery workflow |
| **pdf2john** | Extraction of password hashes from protected PDF files |
| **Wordlists** | Candidate-password testing |

---

## Methodology Overview

The exercise used two different password-recovery workflows.

### NetworkWalks Workflow

```text
Encrypted PDF/File
        ↓
Upload File to NetworkWalks
        ↓
Generate / Obtain Hash
        ↓
Copy the Hash
        ↓
Submit Hash to Password-Cracking Tool
        ↓
Candidate Password Testing
        ↓
Password Recovered
        ↓
Validate the Result
```

### John the Ripper Workflow

```text
Encrypted PDF
        ↓
Copy File to Kali Linux
        ↓
Extract PDF Hash using pdf2john
        ↓
Save Hash to a File
        ↓
Run John the Ripper
        ↓
Wordlist-Based Password Testing
        ↓
Password Recovered
        ↓
Verify Using john --show
```

Detailed procedures for both approaches are documented in:

**[`documentation/methodology.md`](documentation/methodology.md)**

---

## John the Ripper – Example Workflow

The PDF hash was extracted using `pdf2john`:

```bash
pdf2john "My Locked PDF3.pdf" > pdf_hash3.txt
```

The extracted hash was then processed using John the Ripper:

```bash
john pdf_hash3.txt
```

After the password-recovery process completed, the result was verified using:

```bash
john --show pdf_hash3.txt
```

Successful recovery was confirmed with:

```text
1 password hash cracked, 0 left
```

---

## NetworkWalks – Example Workflow

The NetworkWalks training environment was used to understand an alternative password-recovery process.

The general workflow was:

```text
Upload encrypted file
        ↓
Obtain password hash
        ↓
Copy hash
        ↓
Submit hash to the password-cracking tool
        ↓
Test candidate passwords
        ↓
Identify matching password
        ↓
Complete the challenge
```

This provided practical exposure to a password-cracking workflow different from the local John the Ripper approach.

---

## Results

The exercise was successfully completed using both approaches.

### John the Ripper

The Kali Linux terminal output confirmed that the password hash was successfully processed and recovered.

The final verification reported:

```text
1 password hash cracked, 0 left
```

### NetworkWalks

The NetworkWalks challenge environment demonstrated successful password matching and completion of the assigned challenges.

The results provided hands-on experience with:

- Encrypted PDF password recovery
- Password hash extraction
- Wordlist-based password testing
- Offline password-recovery concepts
- Comparing different security-tool workflows

---

## Evidence

Screenshots demonstrating the practical work are available in the [`screenshots/`](screenshots/) directory.

### John the Ripper Results

The John the Ripper screenshots demonstrate:

- PDF hash processing
- Password recovery
- Successful hash verification

### NetworkWalks Results

The NetworkWalks screenshots demonstrate:

- Candidate-password testing
- Successful password matching
- Completion of the assigned cybersecurity challenges

### Screenshot Structure

```text
screenshots/
├── john-results.png
├── networkwalks-results.png
└── cracked-password.png
```

> **Note:** Credentials, passwords, and challenge flags should not be unnecessarily exposed in public repositories. Screenshots should be reviewed and sensitive information should be redacted where appropriate.

---

## Key Security Lessons

### 1. Password Strength Matters

Encrypted files protected with weak or predictable passwords may be vulnerable to offline password-guessing attacks.

### 2. Wordlists Can Be Effective

Password-recovery tools can test large numbers of candidate passwords efficiently when appropriate wordlists are available.

### 3. Password Hashes Require Protection

If an attacker obtains the password hash associated with an encrypted document, they may be able to perform offline password-guessing attempts without continuously interacting with the original application.

### 4. Password Reuse Increases Risk

Using the same or similar passwords across multiple systems or protected files can increase the impact of a compromised password.

### 5. Different Tools Use Different Workflows

Using both NetworkWalks and John the Ripper provided practical exposure to different approaches for password-recovery activities.

### 6. Strong Passwords Improve Security

Long, unique, and unpredictable passwords or passphrases significantly increase resistance to password-guessing attacks.

---

## Ethical Scope

This exercise was performed strictly within an **authorized cybersecurity training environment** using challenge files provided for educational purposes.

The techniques demonstrated in this project should only be used when:

- The file or system is owned by you.
- Explicit authorization has been provided by the owner.
- The activity is part of an approved security assessment, laboratory, or training exercise.

Unauthorized password cracking, credential recovery, or access to protected files may violate organizational policies and applicable laws.

This project is intended for:

- Cybersecurity education
- Security awareness
- Authorized security testing
- Practical security-tool learning

---

## Conclusion

This hands-on exercise provided practical experience in encrypted PDF password recovery using **John the Ripper** and the **NetworkWalks Password Cracking Tool**.

By working with two different tools, the exercise helped develop an understanding of:

- PDF password protection
- Password hashes
- Wordlist-based password testing
- Offline password-recovery concepts
- Security-tool workflows
- Password-security weaknesses
- Secure password-management practices

### Key Takeaway

> **The security of an encrypted document depends not only on the encryption mechanism but also on the strength and management of the password protecting it.**

---

## Disclaimer

This repository is intended strictly for **educational purposes and authorized cybersecurity testing**.

Do not use password-recovery techniques against files, systems, accounts, or data without appropriate authorization.
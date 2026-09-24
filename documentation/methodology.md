# Methodology

## 1. Overview

This document describes the methodology followed during the **Encrypted PDF Password Recovery** cybersecurity lab.

The exercise used two approaches:

1. **NetworkWalks Password Cracking Tool**
2. **John the Ripper on Kali Linux**

The purpose was to understand how different tools can be used to test password-protected files within an authorized cybersecurity training environment.

---

# 2. NetworkWalks Methodology

## Step 1 – Prepare the Encrypted File

An encrypted PDF/file provided as part of the authorized NetworkWalks training exercise was selected for testing.

## Step 2 – Upload the Encrypted File

The encrypted file was uploaded to the NetworkWalks password-cracking tool.

```text
Encrypted PDF/File
        ↓
Upload to NetworkWalks
```

## Step 3 – Obtain the Hash

The tool processed the encrypted file and provided the corresponding password hash.

```text
Encrypted File
        ↓
Hash Generation
        ↓
PDF Password Hash
```

## Step 4 – Copy the Hash

The generated hash was copied from the NetworkWalks interface.

## Step 5 – Submit the Hash

The extracted hash was submitted to the password-cracking functionality provided by the NetworkWalks training tool.

## Step 6 – Candidate Password Testing

The tool tested candidate passwords against the supplied hash.

The process continued until a candidate password matched the password represented by the hash.

## Step 7 – Validate the Result

The recovered password was used to validate the result against the authorized challenge file.

### NetworkWalks Workflow

```text
Encrypted PDF/File
        ↓
Upload to NetworkWalks
        ↓
Generate Hash
        ↓
Copy Hash
        ↓
Submit Hash
        ↓
Candidate Password Testing
        ↓
Matching Password Identified
        ↓
Challenge Validation
```

---

# 3. John the Ripper Methodology

## Step 1 – Prepare the Encrypted PDF

The authorized encrypted PDF was copied to a working directory in the Kali Linux environment.

Example:

```bash
cp "My Locked PDF3.pdf" ~/password-cracking-lab/
```

## Step 2 – Extract the PDF Password Hash

The `pdf2john` utility was used to extract the password hash from the protected PDF.

Example:

```bash
pdf2john "My Locked PDF3.pdf" > pdf_hash3.txt
```

The resulting file contained the information required by John the Ripper for password testing.

## Step 3 – Run John the Ripper

The extracted hash was provided to John the Ripper:

```bash
john pdf_hash3.txt
```

John the Ripper then tested candidate passwords using its configured password list/rules.

## Step 4 – Monitor the Recovery Process

John the Ripper displayed the progress of the password-recovery operation in the Kali Linux terminal.

The process continued until a matching candidate password was identified.

## Step 5 – Verify the Recovered Password

After the recovery process completed, the result was verified using:

```bash
john --show pdf_hash3.txt
```

A successful result was confirmed when John reported:

```text
1 password hash cracked, 0 left
```

### John the Ripper Workflow

```text
Encrypted PDF
        ↓
Copy to Kali Linux
        ↓
pdf2john
        ↓
Extract Password Hash
        ↓
John the Ripper
        ↓
Wordlist-Based Testing
        ↓
Password Recovered
        ↓
john --show
        ↓
Result Verification
```

---

# 4. Comparison of the Two Approaches

| Aspect | NetworkWalks | John the Ripper |
|---|---|---|
| Environment | NetworkWalks training platform | Kali Linux |
| Input | Encrypted file / extracted hash | Extracted PDF hash |
| Hash extraction | Provided through the training workflow | `pdf2john` |
| Password testing | Performed by the training tool | Performed locally by JtR |
| Wordlist-based testing | Supported by the training workflow | Supported |
| Result validation | Challenge validation | `john --show` |
| Learning objective | Understand an alternative password-cracking workflow | Understand local password recovery |

The exercise demonstrated that different tools may provide different workflows while addressing the same general security-testing objective.

---

# 5. Results

Both password-recovery approaches were successfully completed in the authorized training environment.

### John the Ripper

The terminal output confirmed successful password recovery:

```text
1 password hash cracked, 0 left
```

### NetworkWalks

The NetworkWalks interface demonstrated successful candidate-password matching and challenge completion.

The results confirmed that the selected candidate passwords matched the passwords protecting the assigned training files.

---

# 6. Security Lessons

## Password Complexity

Weak or predictable passwords can be susceptible to password-guessing attacks.

## Offline Password Attacks

Once an attacker obtains an appropriate password hash, password guessing can potentially be performed offline.

## Wordlist Selection

The effectiveness of a wordlist-based approach depends heavily on the quality and relevance of the candidate-password list.

## Password Reuse

Reusing passwords across multiple systems or files increases the potential impact of a compromised credential.

## Strong Passwords

Long, unique, and unpredictable passwords provide stronger resistance against password-guessing attempts.

## Tool Awareness

Learning multiple security tools provides a broader understanding of how security-testing workflows are implemented.

---

# 7. Ethical Considerations

This exercise was conducted exclusively against authorized training files provided as part of a cybersecurity learning environment.

Password-recovery techniques must only be used when:

- The tester owns the target file/system, or
- Explicit authorization has been provided.
- The activity falls within an approved testing or training scope.

The techniques described in this document must not be used to gain unauthorized access to personal files, corporate systems, accounts, or protected information.

---

# 8. Conclusion

The exercise provided practical experience with two different approaches to encrypted PDF password recovery.

Using **NetworkWalks** provided exposure to an alternative password-cracking workflow, while **John the Ripper on Kali Linux** provided hands-on experience with local hash processing and wordlist-based password recovery.

The exercise reinforced the importance of:

- Strong password selection
- Unique passwords
- Secure password management
- Protection of password hashes
- Authorized security testing
- Understanding multiple cybersecurity tools

The overall objective was to develop practical knowledge of password security and understand how weak passwords can affect the security of encrypted documents.
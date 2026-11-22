# PDF Password Recovery Using John the Ripper | Kali Linux

## Project Overview

This practical exercise was completed as part of my cybersecurity internship training with NetworkWalks.

The objective was to recover the password of a password-protected PDF document using **John the Ripper (JTR)** and its PDF hash extraction utility, PDF2John.

The exercise provided hands-on experience with password hash extraction, dictionary-based password auditing, and password recovery in a Kali Linux environment.

## Practical Objectives

- Understand how password-protected PDF documents are secured.
- Extract PDF password hashes using PDF2John.
- Verify PDF hash format compatibility with John the Ripper.
- Perform a dictionary-based password audit using the RockYou wordlist.
- Verify the password recovery result.

## Tools and Technologies

| Tool            | Purpose                        |
| --------------- | ------------------------------ |
| Kali Linux      | Testing environment            |
| John the Ripper | Password auditing and recovery |
| PDF2John        | PDF password hash extraction   |
| RockYou         | Password dictionary            |
| VirtualBox      | Virtualisation platform        |
| Python 3        | Running the PDF2John script    |

## Practical Implementation

### 1. Transferring the PDF File

The internship PDF was transferred from Windows to Kali Linux using VirtualBox Shared Folders.

The file was copied into the Downloads directory.

### 2. Installing the Required Dependency

The PDF2John utility required the `pyhanko` Python package.

A dedicated Python virtual environment was created to install the dependency without modifying Kali Linux's system Python environment.

### 3. Extracting the PDF Password Hash

The following command was executed:

```bash
python /usr/share/john/pdf2john.py "My Locked PDF1.pdf" > pdf1.hash
```

The command successfully extracted the PDF password hash and saved it in `pdf1.hash`.

### 4. Verifying PDF Format Support

The following command was used:

```bash
john --list=formats | grep -i pdf
```

The output confirmed that PDF was among the supported hash formats.

### 5. Preparing the RockYou Wordlist

The RockYou wordlist was checked using:

```bash
ls -lh /usr/share/wordlists/rockyou.txt
```

The wordlist was available and had a reported size of 134 MB.

### 6. Performing the Password Audit

The following command was executed:

```bash
john --format=PDF --wordlist=/usr/share/wordlists/rockyou.txt pdf1.hash
```

John the Ripper successfully recovered the password from the supplied PDF hash.

**Result:** Password recovery successful.

The recovered password is documented in the private internship evidence, not published in this repository.

## Results and Observations

The practical exercise demonstrated that:

- PDF password hashes can be extracted using PDF2John.
- John the Ripper supports PDF password auditing.
- Dictionary attacks can recover passwords present in the selected wordlist.
- Password complexity and uniqueness are important for protecting PDF documents.

## Screenshots and Evidence

The following screenshots document the practical exercise:

1. VirtualBox shared-folder configuration.
2. PDF files successfully transferred into Kali Linux.
3. PDF password hash extraction.
4. John the Ripper PDF format verification.
5. RockYou wordlist verification.
6. Successful password recovery.

## Key Learning Outcomes

Through this exercise, I gained practical experience in:

- Using John the Ripper in Kali Linux.
- Extracting password hashes from PDF documents.
- Understanding dictionary-based password auditing.
- Working with password wordlists.
- Interpreting password recovery results.
- Documenting cybersecurity laboratory activities.

## Conclusion

This practical strengthened my understanding of password security and offline password auditing.

It also demonstrated why organisations should enforce strong, unique passwords and avoid relying on weak or commonly used passwords to protect sensitive documents.

**Training Provider:** NetworkWalks
**Project:** Cybersecurity & Ethical Hacking
**Module:** Password Cracking with John the Ripper
**Environment:** Kali Linux
**Status:** PDF 1 password recovery completed successfully.

---

*Disclaimer: This exercise was conducted on a PDF document supplied for authorised cybersecurity internship training. All testing was limited to the provided practice material.*

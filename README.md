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



<img width="1778" height="988" alt="j1" src="https://github.com/user-attachments/assets/3aa45d3c-a76c-4e50-972c-9dfc7929c809" />


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



<img width="1778" height="988" alt="j1" src="https://github.com/user-attachments/assets/92e234d9-e6a2-4f34-ab66-21f2ecf245b3" />

<img width="1317" height="801" alt="j2" src="https://github.com/user-attachments/assets/1c1d0d62-9d4f-4cd0-bbce-e0c4037af287" />

<img width="1843" height="824" alt="J3" src="https://github.com/user-attachments/assets/25ec7f0f-34a8-48b9-acb1-bada7181dce0" />

<img width="1919" height="638" alt="J4" src="https://github.com/user-attachments/assets/5fb35371-6f47-41d0-a777-e4c28e4d50b1" />

<img width="1160" height="724" alt="J5" src="https://github.com/user-attachments/assets/22d3d0dc-7cc7-415d-9d37-37d4ee792826" />

<img width="1688" height="777" alt="J6" src="https://github.com/user-attachments/assets/93ea9801-c855-4821-95a8-2a2b05bb591e" />


<img width="916" height="304" alt="J7" src="https://github.com/user-attachments/assets/5b593a52-36ef-4d92-8789-cf6408040cec" />

<img width="947" height="207" alt="J8" src="https://github.com/user-attachments/assets/d918da9c-3112-4421-9b9d-c503a7f6e1ba" />

<img width="913" height="267" alt="J9" src="https://github.com/user-attachments/assets/281070b4-6780-4a36-a900-a5c3f415fe3d" />

<img width="828" height="297" alt="j10" src="https://github.com/user-attachments/assets/6554f683-46db-4e98-9127-1329c5b86362" />

<img width="907" height="822" alt="J11" src="https://github.com/user-attachments/assets/7befe913-8cdc-4ca5-8d2f-02eb6410854b" />

<img width="826" height="865" alt="J12" src="https://github.com/user-attachments/assets/11c28685-4b23-42ad-80b7-dbc181e0ba60" />

<img width="1648" height="956" alt="J14" src="https://github.com/user-attachments/assets/10475813-fec1-4b87-aea3-d61b58a05db6" />

<img width="1026" height="1009" alt="j15" src="https://github.com/user-attachments/assets/ec31149e-12ce-4d9c-a32e-49d7f2e8adac" />

<img width="607" height="716" alt="j16" src="https://github.com/user-attachments/assets/ba73f44d-7a25-4a35-89fa-55afee9dca57" />

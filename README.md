# Cryptography Encryption-Decryption Tool

## Overview

The **Cryptography Encryption-Decryption Tool** is a complete, console-based cryptographic suite implemented in **C**. It provides a comprehensive set of classic and modern encryption algorithms, complete with interactive menus, file persistence, activity logging, and strength analysis. The tool is designed for educational purposes, demonstrating fundamental cryptographic concepts such as string manipulation, modular arithmetic, bitwise operations, and file handling.

---

## Features

- **8 Encryption Algorithms**  
  - Caesar Cipher (shift cipher)  
  - Vigenère Cipher (polyalphabetic substitution)  
  - Reverse Cipher (text reversal)  
  - Atbash Cipher (mirror mapping)  
  - XOR Cipher (bitwise XOR)  
  - RSA Cipher (simplified public-key encryption)  
  - Base64 Encoding  

- **Interactive Menu System** – Easy-to-use prompts for encryption and decryption.

- **History Tracking** – Every encryption/decryption operation is stored with timestamps in a binary file (`encryption_history.dat`).

- **RSA Key Generation** – Generate public/private key pairs with automatic storage (`rsa_keys.dat`).

- **Strength Analysis** – Evaluate the quality of encrypted text based on character diversity, unique characters, and character types.

- **Activity Logging** – All significant actions are logged to `cryptography.log` with timestamps.

- **File Persistence** – Save and load encryption history from disk.

- **Input Validation** – All user inputs are validated to prevent errors.

---

## Algorithms Implemented

| Algorithm       | Type               | Description |
|-----------------|--------------------|-------------|
| **Caesar**      | Substitution       | Shifts each letter by a fixed number. |
| **Vigenère**    | Polyalphabetic     | Uses a keyword to determine variable shifts per character. |
| **Reverse**     | Transposition      | Reverses the entire string. |
| **Atbash**      | Substitution       | Maps each letter to its reverse in the alphabet (A↔Z, B↔Y, …). |
| **XOR**         | Stream cipher      | Bitwise XOR with a repeating key. |
| **RSA**         | Public-key         | Simplified implementation using small primes for demonstration. |
| **Base64**      | Encoding           | Converts binary data to ASCII text using a 64‑character alphabet. |

---

### Prerequisites
- A C compiler (GCC recommended)
- `make` (optional, for using the provided Makefile)
- Standard C libraries (no external dependencies)

### Compile with Make

```bash
make
Compile Manually
bash
gcc -o crypto cryptography.c -lm
Clean Object Files
bash
make clean
Usage
Run the executable:

bash
./crypto
The main menu will appear:

```

========================================
    ENCRYPTION-DECRYPTION TOOL
       Cryptography Suite v1.0
========================================
1. Encrypt Text
2. Decrypt Text
3. View Encryption History
4. Generate RSA Keys
5. Analyze Encryption Strength
6. Save to File
7. Load from File
8. Clear History
9. Exit
========================================
Enter choice:
Follow the on-screen prompts to select algorithms, enter keys, and view results.

File Structure
File	Description
cryptography.c	Main program with all logic and menu integration.
caesar.c	Caesar cipher functions.
vigenere.c	Vigenère cipher functions.
rsa.c	RSA helper functions (prime, gcd, modExp, key generation).
xor.c	XOR cipher functions.
base64.c	Base64 encoding/decoding functions.
utils.c	Utility functions (logging, time formatting).
encryption_history.dat	Binary file storing encryption records.
rsa_keys.dat	Binary file storing RSA key pair.
cryptography.log	Text log of all activities.
README.md	This documentation.
Makefile	Build automation script.
Example Usage
Encrypt with Caesar Cipher
text
Enter choice: 1
=== SELECT ENCRYPTION METHOD ===
1. Caesar Cipher (Simple shift)
2. Vigenere Cipher (Keyword shift)
3. Reverse Cipher (Text reversal)
4. Atbash Cipher (Mirror mapping)
5. XOR Cipher (Bitwise XOR)
6. RSA Cipher (Public key)
7. Base64 Encoding
8. Back to Main
Enter algorithm: 1
Enter text to encrypt: HELLO
Enter shift (1-25): 3

=== ENCRYPTION RESULTS ===
Original: HELLO
Encrypted: KHOOR
Decrypted: HELLO
✅ Decryption successful!
Generate RSA Keys
text
Enter choice: 4
RSA Keys Generated:
Prime1: 7, Prime2: 11
Modulus: 77
Public Key (e): 13
Private Key (d): 37
RSA keys saved to rsa_keys.dat
Strength Analysis
text
Enter choice: 5
Enter original text: HELLO
Enter encrypted text: KHOOR

=== ENCRYPTION STRENGTH ANALYSIS ===
Original Length: 5 chars
Encrypted Length: 5 chars
Unique Characters: 4
Character Diversity: 80%
Character Types: Uppercase=5, Lowercase=0, Digits=0, Special=0
Strength: STRONG 🔒🔒
Recommendation: Good for general use

---

## Notes
RSA is simplified – uses small primes (≤ 47) and works only with numeric messages smaller than the modulus. It is intended for learning, not for real-world security.

Base64 – Encodes and decodes according to RFC 4648, with proper padding.

History – Stores up to 100 records; older records are overwritten when full.

All algorithms support both encryption and decryption; the tool handles key input and validation automatically.

---

## Contributing

Contributions are welcome! Please follow these steps:

Fork the repository.

Create a feature branch.

Commit your changes.

Open a pull request with a clear description of the changes.

---

## License

This project is licensed under the MIT License – see the LICENSE file for details.
---

## Acknowledgments
Inspired by classic cryptography textbooks and online resources.

Built as a comprehensive demonstration of C programming skills and cryptographic concepts.

Happy Cryptography! 🔐

---

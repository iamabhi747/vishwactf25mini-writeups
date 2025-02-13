# Architect Enigma

## Challenge Description
We were given an executable file and a cryptic description referencing blueprints, coordinates, and scattered fragments. The hints suggested analyzing different checkpoints, but we focused on a direct approach to reverse-engineering the binary.

### Given File:
- **i_want_answers2.exe** (Executable containing the encrypted flag)

## Approach to Decryption

1. **Analyzing the Executable**
   - Opened `i_want_answers2.exe` in **Binary Ninja** for static analysis.
   - Identified a decryption function embedded within the code.

2. **Recognizing the Cipher**
   - The function’s name and logic strongly indicated a **Caesar cipher**.
   - The encrypted flag was processed using a simple character shift.

3. **Decrypting the Flag**
   - Knowing the flag format (`VishwaCTF{...}`), we used **VishwaCTF** as known plaintext.
   - Quickly reversed the Caesar cipher shift to reveal the full flag.

## Conclusion
This challenge was efficiently solved by recognizing a **Caesar cipher** in the decryption function. Instead of following the provided hints, we took a **reverse-engineering approach** and leveraged known plaintext to recover the flag without diving deep into the assembly code.


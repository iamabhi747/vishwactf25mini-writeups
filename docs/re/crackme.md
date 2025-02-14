# Solving the "Crack Me" CTF Challenge

## Challenge Description
The challenge provided an executable file with minimal hints. Our task was to analyze it and recover the hidden flag.

### Given File:
- **exploit.exe** (Executable containing the encrypted flag)

## Approach to Decryption

1. **Analyzing the Executable**
   - Opened `exploit.exe` in **Binary Ninja** for static analysis.
   - Identified a **decryption function** within the code.

2. **Recognizing the Cipher**
   - The function’s logic revealed it was implementing a **Caesar cipher**.
   - The encrypted flag was processed using a simple character shift.

3. **Decrypting the Flag**
   - Knowing the flag format (`VishwaCTF{...}`), we used **VishwaCTF** as known plaintext.
   - Quickly reversed the **Caesar cipher shift** to reveal the full flag.

## Conclusion
By utilizing **reverse engineering** techniques, we identified and quickly decrypted a **Caesar cipher** without needing extensive analysis. Recognizing the cipher type early led to a rapid solution.
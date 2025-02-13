# Encrypted Canvas

## Challenge Description
We were given an encrypted file and a key file, with a hint suggesting that the key to unlocking the encryption was hidden in plain sight. Our objective was to decrypt the file and extract the flag.

### Given Files:
- **Encrypted_Canvas.txt** (The encrypted data)
- **keysecret.txt** (Contains a sequence of binary numbers)

## Approach to Decryption

1. **Identifying the Encryption Method**
   - The structure of `Encrypted_Canvas.txt` resembled **Fernet encryption**.
   - The key file contained a binary sequence of `10`.
   
2. **Extracting the Key**
   - Using CyberChef, we converted the binary sequence from `keysecret.txt` to ASCII.
   - This resulted in a **Base64-encoded Fernet key**.
   
3. **Decrypting the Encrypted File**
   - Using Python and the **cryptography** library, we decrypted `Encrypted_Canvas.txt` with the extracted key.
   - The output was a **.gif file** containing 64 frames.
   
4. **Extracting the Flag**
   - Each frame appeared to contain a **small part of the flag**.
   - Using **Photoshop**, we overlaid all frames to reveal the complete flag.
   
## Conclusion
This challenge demonstrated a multi-step cryptanalysis process, involving **Fernet decryption**, **binary-to-text conversion**, and **image processing**. By systematically uncovering each layer, we successfully extracted the hidden flag.


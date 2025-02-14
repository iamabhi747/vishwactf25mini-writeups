# Faulpelz

## Challenge Description
The challenge involved recovering a secret message that was encrypted and encoded. The given clues included a Huffman tree traversal and a binary-encoded message.

### Given Files:
- **chall.exe** (Executable performing encryption and encoding)
- **Message:** `001101111000010110010110001111100110101001110110`
- **Pre-Order Traversal:** `IIILQLHIILALBILULGIILKLEIILPLNLF`

## Approach to Decryption

1. **Reverse Engineering the Executable**
   - Opened `chall.exe` in **Binary Ninja**.
   - Identified the encryption process:
     - **Vigenère cipher** with key **"ctfworld"**.
     - **Huffman encoding** applied after encryption.

2. **Decoding the Huffman Encoding**
   - Used the given **pre-order traversal** to reconstruct the **Huffman tree**.
   - Decoded the **binary sequence** back into the **Vigenère-encrypted message**.

3. **Decrypting the Vigenère Cipher**
   - Used the known key **"ctfworld"** to decrypt the obtained message.
   - Successfully recovered the original plaintext message.

## Conclusion
By utilizing **reverse engineering**, **Huffman decoding**, and **Vigenère decryption**, we successfully recovered the hidden message and extracted the final flag: `VishwaCTF{message-decoded}`.


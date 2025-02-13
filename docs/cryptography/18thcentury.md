# 18th Century

## Challenge Description
We were given an encrypted string and a hint that suggested a mathematical progression was used for encryption. The hint led to the idea that a well-known mathematician’s work with numbers and intrinsic progressions played a key role in the encryption method.

### Given Data:
- **Encrypted String:** `fVngv&ex6x+izZg)4ex]Z`
- **Flag Format:** `VishwaCTF{Decrypted_String}`

## Approach to Decryption

1. **Identifying the Encryption Method**
   - Classical ciphers like Caesar, Vigenère, and Fibonacci-based shifts did not yield correct results.
   - A deeper mathematical approach was needed.
   
2. **Using Euler’s Totient Function**
   - Euler’s Totient Function, `φ(n)`, counts the integers up to `n` that are coprime with `n`.
   - It provides a structured sequence of values that could be used as character shifts.
   - By generating the totient values for indices of the encrypted text and reversing the shifts, we decrypted the message.
   
3. **Decryption Process**
   - Compute `φ(n)` for each position in the encrypted string.
   - Reverse the shift by subtracting the corresponding `φ(n) % 26` from each character.
   - Convert back to plaintext.
   
4. **Recovered Plaintext**
   - The decrypted string was **"Euler_Totient_Is_FUN"**.
   - The final flag: **`VishwaCTF{Euler_Totient_Is_FUN}`**.

## Conclusion
This challenge required recognizing Euler’s Totient Function as the key to encryption. By leveraging number theory and modular arithmetic, we successfully decrypted the message. Euler’s Totient Function is a powerful tool in cryptography, often appearing in RSA and related cryptosystems.


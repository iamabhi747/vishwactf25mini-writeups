# Time Stuck

## Challenge Description
We were given an encrypted message and a hint suggesting that the encryption was tied to a specific moment in time when "the hands of time met at a perfect alignment." The given Python script used AES encryption in ECB mode, with keys derived from timestamps through SHA-256 hashing.

### Given Data:
- **Ciphertext:** `voqHAsJ3XIngohsGRx9iTNsSTC/LCMZVV8nQ25/+tGCNmuB+PVYEt9V9gWAWPNPd`
- **Key Generation:** Based on two specific timestamps.

## Approach to Decryption

1. **Understanding the Encryption Mechanism**
   - The encryption used AES in ECB mode.
   - Two timestamps were used to generate SHA-256 keys.
   - The decryption required reversing the process using the correct timestamps.

2. **Determining the Epoch Time**
   - The hint suggested that the key timestamps were aligned with a significant moment.
   - The start time was assumed to be **2025-02-01 00:00:00**.
   - The second timestamp was **5 minutes later**.

3. **Brute-Forcing the Correct Timestamps**
   - We iterated through a 24-hour window, generating possible timestamp pairs.
   - For each pair, we attempted decryption.
   - When the correct timestamps were found, the decrypted message was revealed.

4. **Recovered Plaintext**
   - After iterating through the possible timestamps, we successfully decrypted the message.
   - The final flag was extracted.

## Conclusion
This challenge required recognizing the significance of timestamps in AES key generation. By leveraging a brute-force approach on a limited time window, we successfully decrypted the message. Time-based cryptographic techniques are commonly used in security mechanisms, and understanding their weaknesses is crucial in cryptanalysis.


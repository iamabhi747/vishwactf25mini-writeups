# Pay Your Own Loan

## Challenge Description
No description was provided.

### Given Files:
- IP address of the deployed challenge

---

### Solving Process:
This was a web challenge where we exploited the server's functionality in multiple layers.

1. **Initial Interaction:**
   - Upon visiting the page, we were greeted with a heading and a single button labeled "Pay Loan."
   - Clicking the button displayed:
     - Transaction ID: `xft2a552wd53e1adw33dfeesg36`
     - UTR (Unique Transaction Reference): `xup-icpmxgz-mzhhefYE`
   - Inspecting the script and local storage revealed another variable, `sesToken`:
     ```javascript
     const transactionId = "xft2a552wd53e1adw33dfeesg36";
     const ciph0 = "xup-icpmxgz-mzhhefYE";
     const sesToken = "Sp6Tq7Q1ZsJHNpm888eke";
     ```
   - A hidden image, `kmatrix.png`, contained a sequence of numbers: `8 11 20 15 2 9 15 21 10`.
   - The image alt text: **Hill 3x3**, suggesting the **Hill cipher** encryption method.

2. **Deciphering UTR (ciph0):**
   - The given sequence was used as a key matrix for Hill 3x3 cipher.
   - Decrypting `ciph0` resulted in: **"ark-banking-portalZZ"**.
   - Ignoring "ZZ" (as per challenge hint), we got the endpoint: `/ark-banking-portal`.

3. **Accessing Banking Portal:**
   - The page contained an input for the transaction ID and an "Approve Transaction" button.
   - Upon attempting approval, the server responded with:
     ```
     📩 Server: ❌ Missing 'x-banking-auth'
     ```
   - We needed to determine how `x-banking-auth` was generated.

4. **Extracting x-banking-auth:**
   - JavaScript code snippet (commented-out) hinted at Base62 encoding:
     ```javascript
     // const 62 = 0x45ma_;
     // const 0xAuth = _ciph0x_62(sesToken) + _deciph0x62("3Q3ftwMQQWK56VOFRpbSxJ");
     ```
   - We confirmed `0xAuth` required Base62 encoding of `sesToken` and concatenation with another Base62-decoded string.
   - Using CyberChef, we encoded `sesToken` with Base62, decoded the given string, concatenated them, and obtained `x-banking-auth`.

5. **Bypassing WebSocket Security:**
   - The transaction approval process used WebSockets, preventing direct header modification.
   - Using Burp Suite:
     - Intercepted the WebSocket request.
     - Injected `x-banking-auth` into the handshake.
     - Forwarded the request.
   - Successfully approved the transaction and retrieved the **flag!**

---

### **Key Takeaways:**
- **Multiple encryption layers:** Hill cipher and Base62 encoding.
- **Hidden authentication mechanism:** `x-banking-auth` required manual extraction.
- **WebSocket interception:** Necessary to modify request headers for authentication bypass.

---

**Flag Format:** `VishwaCTF{...}`

---


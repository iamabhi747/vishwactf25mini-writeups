# Whispering Wings

## Challenge Description
A hidden message lay within an image, concealed layer by layer. The challenge hinted at a cipher associated with **Beaufort** and **butterflies**, guiding us toward uncovering the encrypted flag.

### Given File:
- **Wings_of_SKY.png** (An image containing hidden data)

## Approach to Decryption

1. **Extracting Hidden Data**
   - Ran `exiftool` on **Wings_of_SKY.png**.
   - Found a **Base64-encoded string** in the **User Comment** section.
   - Decoded it to reveal the encrypted flag: `QwxbhoNAZ{Qf0Y%3_i!cC$_mKu3@1pB!}`.

2. **Identifying the Cipher**
   - The description referenced **Beaufort** and **butterflies**, hinting at the **Beaufort cipher**.
   - Used `VishwaCTF` (known plaintext) to determine the partial key: `lepidopte`.

3. **Determining the Full Key**
   - **Lepidoptery** (study of butterflies) matched the theme.
   - Guessed the complete key: **lepidoptera**, using WordHippo.
   
4. **Decrypting the Flag**
   - Used the **Beaufort cipher** with the recovered key.
   - Successfully decrypted the flag: `VishwaCTF{Bv0N%3_w!nG$_rEv3@1eD!}`.

## Conclusion
By leveraging **Exif metadata analysis**, **pattern recognition**, and **Beaufort cipher decryption**, we efficiently uncovered the flag. The key was cleverly hidden in the challenge theme, leading to a quick solution.


# 🦸 Hero Puzzle: Protect the Philippines from the China Sea

This is my methodology for a CTF activity for my course **NSSECU1**.

**Tip:** Explore the Philippines and find the Hero that will protect us from China Sea!!

---

## 🌊 China Sea
    VTJGc2RHVmtYMTliVVAwYVZWclIyV0dSb09LSzZERUlHZVg4SmhuTVJtNjRoWWcwWGxnZjJ6Yy93QjdtSE8xSEJsa1cvMEY0dWhvY3FNN1M4NzNCNmc9PQ==

## 🥥 Luzon
    V293LCB5b3UgZGVjb2RlZCB0aGlzIG1lc3NhZ2UsIGJ1dCB1bmZvcnR1bmF0ZWx5LCBpdCBpcyBpbiBWaXNheWFzLg==

## 🌴 Visayas
    ZPZgBveod0ncRdL4ILq5NZwA27aUFjR4IQ7oCUG2/3Xfc9SKHiemRBvLdOxDa7moX8yqJn/ixrUDQfg3jONsmO3t0CcSAXfgcnc/nsN948+oqPoWMEj5sHyNJg1XnaKXYKOzOJKyeCeXN70Hc6IDFSjKPsuYqbjr1dCpvTdUxLWse4oQKW5xOVmfhsErRoYLr/SugzANzYswdHruqvn6sJrsVIPDjySvDH1JpI2jvhPyDfsQWJ9mggTXpiHt1tXj

## 🏝️ Mindanao
    a9021e02be5317f568b9be734858d0b9873ba98b8ca0d40bfab52d21139e5d39d3cec3e3ca6615fd232c3a4d3d87dee1bee115495c11b529a61deb944e44dd0f

# 🔑 Identifying the Strings
| Region | Encryption Method |
|--------|-------------------|
|China Sea|Base64|
|Luzon|Base64|
|Visayas|Base64|
Mindanao|SHA-512|

---

# 🕵️‍♂️ Decrypting the message
### 1. China Sea - base64 ➡️ plain text
Decoded base64:

    U2FsdGVkX19bUP0aVVrR2WGRoOKK6DEIGeX8JhnMRm64hYg0Xlgf2zc/wB7mHO1HBlkW/0F4uhocqM7S873B6g==
> This appears to be AES-256 encrypted. This means we will need a key to decrypt this, so we will skip this for now.

---

### 2. Luzon - base64 ➡️ plain text
Decoded base64:
    
    Wow, you decoded this message, but unfortunately, it is in Visayas.

    go to viasayas
> Hint: Go to visayas

---

### 3. Visayas - base64 ➡️ plain text (Part 1)
Decoded base64:

    Wow, you decrypt me! Here's the Key: 

    U2F2ZSB0aGlzIHRpcCBmb3IgbGF0ZXI6IFJHVmpiMlJsSUVOb2FXNWhJSE5sWVNCaVlYTmxOalFnWVdkaGFXNGdkRzhnY21WMlpXRnNJSFJvWlNCeVpXRnNJR05wY0dobGNuUmxlSFE9
> Another base64 string. We will decode it next.

---

### 4. Visayas - base64 ➡️ plain text (Part 2)
Decoded base64 string from 3:

    Save this tip for later: RGVjb2RlIENoaW5hIHNlYSBiYXNlNjQgYWdhaW4gdG8gcmV2ZWFsIHRoZSByZWFsIGNpcGhlcnRleHQ=
> String is still base64. Decode it again.

---

### 5. Visayas - base64 ➡️ plain text (Part 3)
Decoded base64 string from 4:

    Decode China sea base64 again to reveal the real ciphertext
> Message complete. Note: We will revisit China Sea with this information later.

---

### 6. Mindanao - SHA-512 hash ➡️ plain text
Decoded SHA-512 string:

    mommy
> This is likely the AES-256 key for China Sea.

---

### 7. China Sea - AES-256 ➡️ plain text
Decrypting AES-256 using key 'mommy':

    45ffcedfae7a674b6cbcd8eaada22383
>This appears to be an MD5 hash.

---

### 8. China Sea - MD5-256 ➡️ plain text
Decoded Md5:

    harambe

---

# 🏆 Final Answer
The hero that will protect the Philippines from the China Sea is **Harambe**! 🦍


## License
This project is licensed under the Creative Commons - see the [LICENSE](https://github.com/elkumo/NSSECU1-CTF1/blob/main/LICENSE) file for details.
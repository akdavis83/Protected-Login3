# Less Secure Login Page with AES Encryption:

# 1.Login Page:
-Generate a SHA-256 hash from the username and password.
-Use the hash to derive an AES key.
-Encrypt a known identifier (e.g., "admin") with AES and store it in sessionStorage.

# 2.Admin Page:
-Retrieve the encrypted token from sessionStorage.
-Derive the AES key using the same hashing method with the same username and password.
-Decrypt the token. If the decrypted result matches the expected identifier, allow access.

# 3.Benefits of Combining AES and SHA-256:
-Deterministic Key Generation: Using SHA-256 to derive an AES key based on the username and password means you don’t need to store the key explicitly. It’s generated securely every time.
-Obfuscation and Security: AES encryption obfuscates the session identifier, making it harder for someone to reverse-engineer access by simply looking at the encrypted data in sessionStorage.

# 4.Limitations:
This approach strengthens security for client-side storage and validation in local applications or demos but remains less secure than server-side validation, which is necessary for production-level authentication.
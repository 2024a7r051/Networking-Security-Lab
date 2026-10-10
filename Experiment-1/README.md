# Experiment 1: Caesar Cipher and Vigenere Cipher

## 1. Caesar Cipher

### Code

text = input("Enter plaintext: ")
shift = int(input("Enter shift: "))

encrypted = ""

# Encryption
for char in text:
    if char.isalpha():
        encrypted += chr((ord(char.upper()) - 65 + shift) % 26 + 65)
    else:
        encrypted += char

decrypted = ""

# Decryption
for char in encrypted:
    if char.isalpha():
        decrypted += chr((ord(char.upper()) - 65 - shift) % 26 + 65)
    else:
        decrypted += char

print("\nCAESAR CIPHER")
print("Plaintext :", text)
print("Encrypted :", encrypted)
print("Decrypted :", decrypted)
print("Verification:", decrypted == text.upper())

### Output
![Caesar Cipher Output](./images/caesar%20output.png)

## 2. Vigenere Cipher

### Code

text = input("Enter plaintext: ")
key = input("Enter key: ").upper()

encrypted = ""

# Encryption
for i in range(len(text)):
    p = ord(text[i].upper()) - 65
    k = ord(key[i % len(key)]) - 65
    encrypted += chr((p + k) % 26 + 65)

decrypted = ""

# Decryption
for i in range(len(encrypted)):
    c = ord(encrypted[i]) - 65
    k = ord(key[i % len(key)]) - 65
    decrypted += chr((c - k) % 26 + 65)

print("\nVIGENERE CIPHER")
print("Plaintext :", text)
print("Encrypted :", encrypted)
print("Decrypted :", decrypted)
print("Verification:", decrypted == text.upper())

### Output
![Vigenere Cipher Output](./images/vigenere%20output.png)







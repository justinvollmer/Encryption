# AES Encryption in TypeScript and Java

This repository contains implementations of AES encryption in TypeScript and Java, utilizing 256-bit CryptoKeys. The TypeScript implementation focuses on AES-GCM encryption, while the Java implementation provides a standard AES encryption.

## Java Implementation

### Part 1: Java Encryption Class (Encryption.java)

The Java implementation uses the `Encryption` class, providing methods for encryption and decryption. Key management, algorithm selection, and static methods for encryption without class instantiation are included.

#### Usage:

```java
// Instantiate Encryption class
Encryption encryption = new Encryption("your256bitKey", "AES");

// Encrypt
String encryptedText = encryption.encrypt("plainText");

// Decrypt
String decryptedText = encryption.decrypt(encryptedText);
```

#### Static Methods:

- `encrypt` and `decrypt` for direct encryption without class instantiation.
- `printAlgorithmList` to display supported algorithms.
- `generateKey` to generate a random 256-bit key.

## TypeScript Implementation

### Part 2: TypeScript Encryption Functions

The TypeScript implementation provides encryption functions using the AES-GCM algorithm. The functions support asynchronous encryption, decryption, key export/import, and key generation.

#### Usage:

```ts
import {
  encrypt,
  decrypt,
  exportKeyToString,
  importStringToKey,
  generateCryptoKey,
} from './encryptionFunctions';

// Generate CryptoKey
const key = await generateCryptoKey();

// Encrypt
const encryptedText = await encrypt('plainText', key);

// Decrypt
const decryptedText = await decrypt(encryptedText, key);

// Export and Import Key as String
const keyString: string = await exportKeyToString(key);
const importedKey: CryptoKey = await importStringToKey(keyString);
```
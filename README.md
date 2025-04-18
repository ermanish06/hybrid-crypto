# HybridCrypto

A secure AES-256-CBC encryption/decryption PHP library with flexible IV handling.

## Features

- AES-256-CBC encryption
- Secure 32-byte key and 16-byte IV
- Supports fixed or random IVs
- File encryption & decryption
- Composer/PSR-4 autoload ready

## Installation

```bash
composer require ermanish06/hybrid-crypto
```

## Usage

```php
use Crypto\HybridCrypto;

$crypto = new HybridCrypto('.key'); // Use random IV (default)
// $crypto = new HybridCrypto('.key', true); // Use fixed IV

$encrypted = $crypto->encrypt("My secret");
$decrypted = $crypto->decrypt($encrypted);

echo $decrypted;
```

## Generate Key File

```php
$crypto = new Crypto\HybridCrypto();
$crypto->generateKeyFile(); // creates .key file with base64 key and IV
```

## File Encryption

```php
$crypto->encryptFile("input.txt", "output.enc");
$crypto->decryptFile("output.enc", "output.txt");
```

## License

MIT

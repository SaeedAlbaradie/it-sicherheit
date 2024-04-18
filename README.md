# Aufgabe 1
## openssl version: 
OpenSSL 3.2.1 30 Jan 2024 (Library: OpenSSL 3.2.1 30 Jan 2024)

# Aufgabe 2

## Eine Datei opensslAufgabe.txt wurde erstellt
touch opensslAufgabe.txt
## Dateieingabe
touch opensslAufgabe.txt
Saeed Albaradie
s_albaradie21@stud.hwr-berlin.de
## Der kryptografische Fingerabdruck mit den MD5 Verfahren:
openssl dgst -md5 opensslAufgabe.txt > opensslAufgabe-md5.txt
## Der kryptograifsche Fingerabdruck mit den SHA3-256 Verfahren:
openssl dgst -sha3-256 opensslAufgabe.txt > opensslAufgabe-sha3-256.txt

# Aufgabe 3
## Die Datei email.txt mittels des AES-256 Verfahren verschlüsselt
openssl enc -aes-256-cbc -salt -in opensslAufgabe.txt -out opensslAufgabe-aes256.enc -pass pass:s_albaradie21@stud.hwr-berlin.de -pbkdf2 -iter 10000
## opensslAufgabe-aes256.enc entschlüsselung:
openssl enc -aes-256-cbc -d -in opensslAufgabe-aes256.enc -out opensslAufgabe-aes-decoded.txt -pass pass:s_albaradie21@stud.hwr-berlin.de -pbkdf2 -iter 10000


# Aufagbe 4
| OS                     | Software (Library)    | Algorithms          |
|------------------------|-----------------------|---------------------|
| Win, Linux, MacOS      | OpenSSL               | SHA AES RSA TLS     |
| Win                    | Microsoft CryptoAPI   | SHA AES RSA TLS     |
| Linux, MacOS, Win      | GnuPG                 | SHA AES RSA TLS     |
| Linux, MacOS, Win      | LibreSSL              | SHA AES RSA TLS     |
| Linux, MacOS, Win      | Botan                 | SHA AES RSA TLS     |
| Win                    | BitLocker             | AES                 |
| Win, MacOS, Linux      | Bouncy Castle         | SHA AES RSA TLS     |
| Win, MacOS, Linux      | Cryptography (Python) | SHA AES RSA         |
| Win, MacOS, Linux      | GnuTLS                | SHA AES RSA TLS     |
| Win, MacOS, Linux      | NSS                   | SHA AES RSA TLS     |
| Win, MacOS, Linux      | PGP                   | RSA AES             |
|------------------------|-----------------------|---------------------|

# Aufgabe 5
## Private Key Generierung:
openssl genpkey -algorithm rsa -out private_key.pem -pkeyopt rsa_keygen_bits:1024

## Public Key Extrahierung:
openssl rsa -pubout -in private_key.pem -out public_key.pem

## Die opensslAufgabe.txt Datei Verschlüsselung:
openssl pkeyutl -encrypt -inkey public_key.pem -pubin -in opensslAufgabe.txt -out opensslAufgabe-rsa.enc

## Die opensslAufgabe-rsa.enc Datei Entschlüsselung:
openssl pkeyutl -decrypt -inkey private_key.pem -in opensslAufgabe-rsa.enc -out opensslAufgabe-decrypted-rsa.txt

# Aufgabe 6
| Unternehmen             | Domain               |
|-------------------------|----------------------|
| Let’s Encrypt           | www.lencr.org        |
| Oracle                  | www-cs-02.oracle.com |
| Amazon                  | www.amazon.com       |
| Google                  | *.google.com         |
| Microsoft               | www.microsoft.com    |
|-------------------------|----------------------|

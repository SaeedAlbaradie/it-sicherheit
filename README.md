# Aufgabe 1
openssl version
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

## Aufgabe 3
### Die Datei email.txt mittels des AES-256 Verfahren verschlüsselt
openssl enc -aes-256-cbc -salt -in opensslAufgabe.txt -out opensslAufgabe-aes256.enc -pass pass:s_albaradie21@stud.hwr-berlin.de -pbkdf2 -iter 10000
### opensslAufgabe-aes256.enc entschlüsselung:
openssl enc -aes-256-cbc -d -in opensslAufgabe-aes256.enc -out opensslAufgabe-aes-decoded.txt -pass pass:s_albaradie21@stud.hwr-berlin.de -pbkdf2 -iter 10000


Aufagbe 4
OS	Software (Library)	Algorithms
Win, Linux, MacOS	OpenSSL	SHA AES RSA TLS
Win	Microsoft CryptoAPI	SHA AES RSA TLS
Linux, MacOS, Win	GnuPG	SHA AES RSA TLS
Linux, MacOS, Win	LibreSSL	SHA AES RSA TLS
Linux, MacOS, Win	Botan	SHA AES RSA TLS
Aufgabe 5
Der folgende Kommando generiert einen Private Key, welche den Public Key ebenfalls beinhaltet.

openssl genrsa -out keypair.pem 1024
Der Public Key muss vom Private Key extrahiert werden:

openssl rsa -in private_key.pem -pubout -out public_key.pem
Das gerade erstellte Schlüssel Paar kann mit den folgenden zwei Kommandos genutzt werden um die email.txt Datei zu verschlüsseln in die Datei public_key_enc_email.txt und zu entschlüsseln in die Datei dec_email.txt

openssl pkeyutl -encrypt -pubin -inkey  keys/public_key.pem -in email.txt -out public_key_enc_email.txt
openssl pkeyutl -decrypt -inkey keys/private_key.pem -in public_key_enc_email.txt -out dec_email.txt
Aufgabe 6
DigiCert, Inc.
Google Trust Service LLC
Microsoft Corporation
D-Trust GmbH
Amazon
Apple Inc.
Sectigo Limited
Let's Encrypt

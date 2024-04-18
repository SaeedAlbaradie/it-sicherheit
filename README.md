# Aufgabe 2
Die Datei email.txt wird als Schlüssel genutz für die Folgeaufgaben. Der kryptografische Fingerabdruck mit den MD5 Verfahren kann mit dem folgenden Kommando erzeugt und in die Datei md5_email.txt gespeichert werden:

openssl dgst -md5 email.txt > md5_email.txt
Der kryptograifsche Fingerabdruck mit den SHA3-256 Verfahren kann mit dem folgenden Kommando erzeugt und in die Datei sha3-256_email.txt gespeichert werden:

openssl dgst -sha3-256 email.txt > sha3-256_email.txt
Aufgabe 3
Mit dem folgenden Kommando wird die Datei email.txt mittels des AES-256 Verfahren verschlüsselt. Als Schlüssel wird die email.txt Datei genutzt.

openssl enc -aes-256-cbc -in email.txt -out aes-256-cbc_email.txt -pass file:email.txt
Die aes-256-cbs_email.txt Datei kann mithilfe des folgenden Kommandos entschlüsselt werden:

openssl enc -d -aes-256-cbc -in aes-256-cbc_email.txt -out decr.txt -pass file:email.txt 
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

# Step by Step

1. Generate private key

    openssl genrsa -out test.pem
    openssl genrsa -out test.pem 4096

2. Generate public key from private key

    openssl rsa -in test.pem -pubout > test.pub

3. Sign file message.txt with private key

    openssl dgst -sha1 -sign test.pem -out ./../message.sign ./../message.txt

4. Verify with public key

    openssl dgst -sha1 -verify test.pub -signature ./../message.sign ./../message.
    
5. Create self-sign

    openssl req -key test.pem -new -x509 -days 365 -out test.crt

6. See cert

    openssl x509 -in test.crt -text -noout

7. Store private key and cert in PKCS12 file

    openssl pkcs12 -inkey test.pem -in test.crt -export -out test.p12

8. Convert PKCS12 to PEM

    openssl pkcs12 -in test.p12 -nodes -out test-pkcs.pem
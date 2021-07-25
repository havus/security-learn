# Step by Step

1. Generate key pair

    ssh-keygen -f test

2. convert to .pem like openssl

    ssh-keygen -p -m PEM -f test

    from:
    -----BEGIN OPENSSH PRIVATE KEY-----
    to:
    -----BEGIN RSA PRIVATE KEY-----

3. 
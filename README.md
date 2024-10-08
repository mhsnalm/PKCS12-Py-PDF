## To run this:
- `pip3 install -r requirements.txt`
- Refer to [the tutorial](https://www.thepythoncode.com/article/sign-pdf-files-in-python) on how to run the script.

## Generate Self-Signed Certificate

```bash
openssl genrsa -aes128 -out server.key 4096
openssl req -new -key server.key -out server.csr
# cp server.key server.key.org
# openssl rsa -in server.key.org -out server.key
openssl x509 -req -days 365 -in server.csr -signkey server.key -out server.crt
openssl pkcs12 -export -out certificate.p12 -inkey server.key -in server.crt
```

## References

https://www.ibm.com/support/pages/how-create-self-signed-certificate-openssl

https://www.ssl.com/how-to/create-a-pfx-p12-certificate-file-using-openssl/

# SSL / TLS

```
// Generate a CSR (Certificate Signing Request)
sudo openssl req -new -newkey rsa:2048 -nodes -keyout app01.key -out app01.csr

// Self-signed Certificate
sudo openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout app01.key -out app01.crt

// Print CSR details
openssl req -noout -text -in app01.csr
```
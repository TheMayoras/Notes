# RENEW CERT

To renew a cert do the following:

1. Remove the IPTABLES rules: `sudo iptables -t nat -F PREROUTING`
2. Renew the cert: `sudo certbot renew`
3. Start SUDO shell: `sudo bash`
4. Renew the cert 
```
openssl pkcs12 \
        -export \
        -in fullchain.pem \
        -inkey privkey.pem \
        -out $PATH_TO_YOUR_CERT_OUTPUT_LOCATION \
        -name tomcat \
        -CAfile chain.pem \
        -caname root
```

5. Restart your server

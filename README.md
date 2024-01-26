# xampp-ssl-config
## Instructions for Windows
 
1. Copy the `crt` directory to the apache directory (e.g. `C:\xampp\apache`).
2. Run the `make-cert.bat` script to generate the server certificate and keys. The server certificate and key will be saved as `crt\{domain}\server.crt` and `crt\{domain}\server.key` respectively.
3. Add the server certficate as trusted certificate by running the command `certmgr.msc`. This will show a window. Right-click on `Trusted Root Certification Authorities > All Tasks > Import..` and click the next button and select the `server.crt` file.
4. Copy the contents of `server.crt` file and append it to `C:\xampp\apache\bin\curl-ca-bundle.crt` with the following text before the certificate contents. Sample shown below. This will enable the curl to use your server certificate.
5. Restart the computer to apply the Trusted Certificate.
```crt
GlobalSign Root CA
==================
-----BEGIN CERTIFICATE-----
...
-----END CERTIFICATE-----
```

## Upcoming
Automated script for windows to perform these steps.

## References
1. https://stackoverflow.com/questions/64800565/how-to-create-valid-ssl-in-localhost-for-xampp
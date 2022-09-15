## Import this CA into a Docker image

```
USER root
ADD https://raw.githubusercontent.com/jacobm3/cosmic-security.net-ca/main/Astronomer-cosmic-security.net-root-a.crt \
  /usr/local/share/ca-certificates
RUN chmod 644 /usr/local/share/ca-certificates/Astronomer-cosmic-security.net-root-a.crt
RUN update-ca-certificates
USER other-user
```

## Import in Ubuntu/WSL2

```
wget https://raw.githubusercontent.com/jacobm3/cosmic-security.net-ca/main/Astronomer-cosmic-security.net-root-a.crt
sudo cp Astronomer-cosmic-security.net-root-a.crt /usr/local/share/ca-certificates
sudo update-ca-certificates
```

## Import in Windows 10

Run PowerShell as Administrator
```
$URL = "https://raw.githubusercontent.com/jacobm3/cosmic-security.net-ca/main/Astronomer-cosmic-security.net-root-a.crt"
$Path = "Astronomer-cosmic-security.net-root-a.crt"

Import-Certificate -FilePath .\Astronomer-cosmic-security.net-root-a.crt -CertStoreLocation Cert:\LocalMachine\Root

```

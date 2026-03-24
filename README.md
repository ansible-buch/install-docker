# Manual installation of Docker Engine

*Please click on the distribution of your choice to view the instructions:*

<details>
<summary><h3>Debian 12, Debian 13</h3></summary>

```bash
# Include distro infos:
source /etc/os-release

# Install required packages:
apt update
apt install -y ca-certificates curl gnupg

# Add Docker's official GPG key:
install -m 0755 -d /etc/apt/keyrings

curl -fsSL https://download.docker.com/linux/${ID}/gpg \
	-o /etc/apt/keyrings/docker.asc

chmod a+r /etc/apt/keyrings/docker.asc

# Add repo to Apt sources:
tee /etc/apt/sources.list.d/docker.sources <<EOF
Types: deb
URIs: https://download.docker.com/linux/${ID}
Suites: $VERSION_CODENAME
Components: stable
Signed-By: /etc/apt/keyrings/docker.asc
EOF

# Install Docker Engine:
apt update
apt install -y docker-ce
```

</details>

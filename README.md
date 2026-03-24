# Manual installation of Docker Engine

*Please click on the distribution of your choice to view the instructions.*


> [!NOTE]
> The following commands require root privileges.
> Run `sudo -i` (or an equivalent command) first.


<details>
<summary><h3>Debian 12+13, Ubuntu 24.04+26.04 LTS</h3></summary>

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


<details>
<summary><h3>Rocky Linux 9+10</h3></summary>

```bash
# Install required packages:
dnf -y install dnf-plugins-core

# Add repo:
dnf config-manager \
	--add-repo https://download.docker.com/linux/centos/docker-ce.repo

# Install Docker Engine:
dnf install docker-ce
```

</details>

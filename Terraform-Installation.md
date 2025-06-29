![image](https://cdn-images-1.medium.com/max/1000/0*GBjuWDTkm88OUdc5.png)

## Terraform Installation

In this demo, We will installing Terraform on a Ubuntu machine.

First, let's verify if the system is up to date and the following packages such as  ```gnupg```, ```software-properties-common```, and ```curl``` are installed. These packaged will be use to verify HashiCorp's GPG signature and install HashiCorp's Debian package repository.

```
sudo apt-get update && sudo apt-get install -y gnupg software-properties-common
```
<br>

We will then install the HashiCorp GPG key.

```
wget -O- https://apt.releases.hashicorp.com/gpg | \
gpg --dearmor | \
sudo tee /usr/share/keyrings/hashicorp-archive-keyring.gpg > /dev/null
```
<br>

We will then verify the key's fingerprint using the ```gpg``` command.

```
gpg --no-default-keyring \
--keyring /usr/share/keyrings/hashicorp-archive-keyring.gpg \
--fingerprint
```
<br>

Add the official HashiCorp repository to your system. The ```lsb_release -cs``` command finds the distribution release codename for your current system, such as ```buster```, ```groovy```, or ```sid```.

```
echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] \
https://apt.releases.hashicorp.com $(lsb_release -cs) main" | \
sudo tee /etc/apt/sources.list.d/hashicorp.list
```
<br>

To update the package information from HashiCorp, we will use the command:
```
sudo apt update
```
<br>

We will then now install terraform using the command:

```
sudo apt-get install terraform
```

To verify and to get more details, we can us the command: ```terraform --help```.





# Inception
FOR ALPINE
get virtualbox from managed software centre

download alpine for i5 (x86_64)
chose new
put in name as inception
type linux
version linux 2.6 64 bit
next
base memory 4096
cores 4 next
disk size 4GB next
finish
go to setting ->storage ->controller IDE ->optical drive ->your alpine download
settings->display->300%
press start(green arrow)
will ask you to login->root -> no need for password initially
setup-alpine

Questions asked by setup-alpine

Example setup-alpine session
The setup-alpine script offers the following configuration options:

Keyboard Layout (Local keyboard language and usage mode, e.g. us and variant of us-nodeadkeys.)
Hostname (The name for the computer.)
Network (For example, automatic IP address discovery with the "DHCP" protocol.)
DNS Servers (Domain Name Servers to query. If unsure, leave DNS domain name blank and using 9.9.9.9 2620:fe::fe for DNS is typically adequate.)
Root password (the password used to login to the root account)
Timezone (Optionally display times/dates in your local time zone)
HTTP/FTP Proxy (Proxy server to use for accessing the web/ftp. Use "none" for direct connections to websites and FTP servers.)
Mirror (From where to download packages. Choose the organization you trust giving your usage patterns to.)
<!-- Contents of /etc/apk/repositories
#/media/cdrom/apks
http://dl-cdn.alpinelinux.org/alpine/v3.19/main
http://dl-cdn.alpinelinux.org/alpine/v3.19/commun -->
Setup a user (Setting up a regular user account)
SSH (Secure SHell remote access server. "OpenSSH" is part of the default install image. Use "none" to disable remote login, e.g. on laptops.)
sshkey->?
Disk Mode (Select between diskless (disk="none"), "data" or "sys", as described above.)
sda ->?


https://www.analyticsvidhya.com/blog/2022/06/writing-dockerfile-is-simple/

VM setup

https://github.com/Bakr-1/inceptionVm-guide.git
Project Guide

https://tuto.grademe.fr/inception/#accueil
https://github.com/codesshaman/inception/blob/main
https://github.com/ChineduGboof/Inception
https://github.com/ChineduGboof/Inception.git
General

https://www.cloudflare.com/learning/ssl/what-is-an-ssl-certificate/
https://youtu.be/pTFZFxd4hOI?si=0-unsQu4Lqf59i4A
https://youtu.be/u-YWtdbpEhQ?si=7m2Wz9luBXP0yC1C
https://wp-cli.org/#:~:text=WP%2DCLI%20is%20the%20command,without%20using%20a%20web%20browser.

1) Download latest stable version of debian
https://www.debian.org/
2) Install virtual box from managed software centre
3) Set up your virtual machine called inception like Born2beRoot tutorial
https://www.youtube.com/watch?app=desktop&v=EunJ4QJaAEw
4) set up nginx
Debian
Install the prerequisites:

	sudo apt install curl gnupg2 ca-certificates lsb-release debian-archive-keyring

Import an official nginx signing key so apt could verify the packages authenticity. Fetch the key:

	curl https://nginx.org/keys/nginx_signing.key | gpg --dearmor \
	    | sudo tee /usr/share/keyrings/nginx-archive-keyring.gpg >/dev/null

Verify that the downloaded file contains the proper key:

	gpg --dry-run --quiet --no-keyring --import --import-options import-show /usr/share/keyrings/nginx-archive-keyring.gpg

The output should contain the full fingerprint 573BFD6B3D8FBC641079A6ABABF5BD827BD9BF62 as follows:

	pub   rsa2048 2011-08-19 [SC] [expires: 2024-06-14]
	      573BFD6B3D8FBC641079A6ABABF5BD827BD9BF62
	uid                      nginx signing key <signing-key@nginx.com>

If the fingerprint is different, remove the file.

To set up the apt repository for stable nginx packages, run the following command:

	echo "deb [signed-by=/usr/share/keyrings/nginx-archive-keyring.gpg] \
	http://nginx.org/packages/debian `lsb_release -cs` nginx" \
	    | sudo tee /etc/apt/sources.list.d/nginx.list

If you would like to use mainline nginx packages, run the following command instead:

	echo "deb [signed-by=/usr/share/keyrings/nginx-archive-keyring.gpg] \
	http://nginx.org/packages/mainline/debian `lsb_release -cs` nginx" \
	    | sudo tee /etc/apt/sources.list.d/nginx.list

Set up repository pinning to prefer our packages over distribution-provided ones:

	echo -e "Package: *\nPin: origin nginx.org\nPin: release o=nginx\nPin-Priority: 900\n" \
	    | sudo tee /etc/apt/preferences.d/99nginx

To install nginx, run the following commands:

	sudo apt update
	sudo apt install nginx

https://docs.docker.com/compose/compose-application-model/

https://wiki.alpinelinux.org/wiki/Alpine_Linux:Overview
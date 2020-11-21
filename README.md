# iauro_nodejs_app

prerequisite:
NAME="Amazon Linux"
VERSION="2"

install:
*docker Docker version 19.03.13-ce, build 4484c46
*docker-compose docker-py version: 3.2.1
                CPython version: 3.6.5
                OpenSSL version: OpenSSL 1.0.1t  3 May 2016
 *git

first clone the repository at /root
git clone https://github.com/AkshayBO/iauro_nodejs_app.git

in ./BackendDemoProject/nginx/default.conf file update your public ip

use below command to get up the application
docker compose up --build

use the below command to to generate ssl certificates-

openssl genrsa -aes128 -out server.key 2048
openssl rsa -in server.key -out server.key
openssl req -new -days 3650 -key server.key -out server.csr
openssl x509 -in server.csr -req -signkey server.key -days 3650

it will return you one .crt file save it as server.crt file
chmod 400 server.*

after that copy the certs at the location-
/root/BackendDemoProject

# apacheguacamole
Docker Compose for Apache Guacamole
0)use ubuntu server 
1)Install Docker
sudo apt update
sudo apt install docker.io -y
sudo snap install docker
sudo systemctl status docker
docker --version
2)Run Docker Without Sudo
sudo groupadd -f docker
sudo usermod -aG docker $USER
newgrp docker
groups

3)Create Folder for Extention
sudo mkdir -p guacamole/guacamole_home/extensions/ 
cd guacamole/guacamole_home/extensions/
sudo wget https://archive.apache.org/dist/guacamole/1.5.3/binary/guacamole-history-recording-storage-1.5.3.tar.gz 
tar -xf guacamole-history-recording-storage-1.5.3.tar.gz
4)Create Record Folder and permission
mkdir guacamole/record
chown -R 1000:1001 guacamole/record
chmod -R 2750 guacamole/record
Clone the GIT repository and start guacamole:
git clone "https://github.com/hamidvb/guacamole-docker-compose.git"
cd guacamole-docker-compose
./prepare.sh

docker-compose up -d
Your guacamole server should now be available at https://ip of your server:8443/. The default username is guacadmin with password guacadmin.


Edit the “Screen Recording” section of one of your existing connection settings. Enter the special value ${HISTORY_PATH}/${HISTORY_UUID} in the “Recording path” input box.



# apacheguacamole
Docker Compose for Apache Guacamole
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

# INSTALLATIONS
## important tools
#### tmux, gnome-tweaks, copyq, xclip, plocate, net-tools, whois

## list of installations
`sudo grep "install " /var/log/apt/history.log | awk -F ' ' '{print $1, $2, $3, $4, $5, $6, $7, $8, $9}' | sort -k1,1 -k2,2`

## installed packages
`dpkg -l`


## installing using curl and apt
```bash
sudo curl https://www.pgadmin.org/static/packages_pgadmin_org.pub | sudo apt-key add
sudo sh -c 'echo "deb http://ftp.postgresql.org/pub/pgadmin/pgadmin4/apt/ubuntu focal pgadmin4" > /etc/apt/sources.list.d/pgadmin4.list'
sudo apt update
sudo apt install pgadmin4
```

## installing using apt
`sudo apt install openjdk-11-jdk`
`sudo update-alternatives --config java`

## installing using apt-get
`sudo apt-get update`
`sudo apt-get install -y mongodb-org`

## install using snap
`snap install kubectl --classic`

## installing a deb file and (using apt-get for dependencies)
`sudo dpkg -i file.deb`
`sudo apt-get install -f`

## installing a tar file
```bash
tar -xvzf postman.tar.gz
sudo mv Postman /opt/Postman
sudo ln -s /opt/Postman/Postman /usr/bin/postman
```

## installing using docker
```bash
sudo docker volume create portainer_data
sudo docker run -d -p 8000:8000 -p 9443:9443 --name portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce:2.21.1
```

- using portainer to view the docker
`https://localhost:9443`
`admin admin@123456`

## installing nvidia driver

## installing cuda
[cuda toolkit](https://developer.nvidia.com/cuda-downloads?target_os=Linux&target_arch=x86_64&Distribution=Ubuntu&target_version=22.04&target_type=deb_local)

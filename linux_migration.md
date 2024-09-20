# INFORMATION
## distro name
lsb_release -a

## architecture
uname -m

## partitions check
sudo blkid

## kernel version
uname -r

## CPU information
lscpu


# SHORTCUTS
## window
win + <arrow>

## terminal
ctrl+alt+T = open terminal
ctrl+L = clear terminal

## copy and paste
Ctrl+Shift+C
Ctrl+Shift+V


# INSTALLATIONS
## important tools
#### tmux, gnome-tweaks, copyq, xclip, plocate, net-tools, whois

## list of installations
sudo grep "install " /var/log/apt/history.log | awk -F ' ' '{print $1, $2, $3, $4, $5, $6, $7, $8, $9}' | sort -k1,1 -k2,2

## installed packages
dpkg -l


## installing using curl and apt
sudo curl https://www.pgadmin.org/static/packages_pgadmin_org.pub | sudo apt-key add
sudo sh -c 'echo "deb http://ftp.postgresql.org/pub/pgadmin/pgadmin4/apt/ubuntu focal pgadmin4" > /etc/apt/sources.list.d/pgadmin4.list'
sudo apt update
sudo apt install pgadmin4

## installing using apt
sudo apt install openjdk-11-jdk
sudo update-alternatives --config java

## installing using apt-get
sudo apt-get update
sudo apt-get install -y mongodb-org

## install using snap
snap install kubectl --classic

## installing a deb file and (using apt-get for dependencies)
sudo dpkg -i file.deb
sudo apt-get install -f

## installing a tar file
tar -xvzf postman.tar.gz
sudo mv Postman /opt/Postman
sudo ln -s /opt/Postman/Postman /usr/bin/postman

## installing using docker
sudo docker volume create portainer_data
sudo docker run -d -p 8000:8000 -p 9443:9443 --name portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce:2.21.1
https://localhost:9443
admin admin@123456

## installing nvidia driver

## installing cuda
[cuda toolkit](https://developer.nvidia.com/cuda-downloads?target_os=Linux&target_arch=x86_64&Distribution=Ubuntu&target_version=22.04&target_type=deb_local)


# ADMINISTRATION
## memory usage
free -h

## disk usage
df -h

## running processes
top -n 1

## network interfaces
ip a

## system uptime
uptime

## active services
systemctl list-units --type=service --state=running

## Checking a service
sudo systemctl status systemd-resolved
sudo systemctl restart systemd-resolved

## Blocking sites
sudo nano /etc/hosts
sudo systemd-resolved --flush-caches

## chat using netcat and telnet
receiver-> nc -l -p 1234
sender-> telnet ip 1234

## Add custom shortcuts
1. Settings -> Keyboard -> Keyboard Shortcuts -> View and customize shortcuts -> Custom Shortcuts::
2. Click on the + button
3. Name it "Open File Manager"
4. Set the command to nautilus (GNOME) or xdg-open
5. Click on the "Set Shortcut" button and press Super + E to assign it.

## clipboard manager
sudo apt install copyq
_Custom shortcuts_
ctrl+alt+z = main window
ctrl+alt+a = tray menu

## handling markdown
reader app: glow
editor and reader: typora

## GNOME extensions
install [gnome-browser-integration](https://chromewebstore.google.com/detail/gnome-shell-integration/gphhapmejobijbbhgpjhcjognlahblep)
install [gnome extention](https://extensions.gnome.org/extension/1160/dash-to-panel/)


# SOFTWARES
## Postgres
sudo apt update
sudo apt install postgresql postgresql-contrib

#### log into postgres
sudo -i -u postgres

#### get into interactive terminal
psql
createdb mydatabase
createuser myuser --superuser --pwprompt
```sql
ALTER USER postgres WITH PASSWORD 'newpassword';
```

#### connect to db
psql -d mydatabase

#### exit from psql command line
\q

#### logout postgres user shell
exit

## VS Code settings
change  Title Bar Style to custom to remove the title bar.

## Create a desktop entry
sudo nano /usr/share/applications/postman.desktop
```bash
[Desktop Entry]
Name=Postman
Exec=/opt/Postman/Postman
Icon=/opt/Postman/app/resources/app/assets/icon.png
Terminal=false
Type=Application
Categories=Development;
```

## tmux
```
ctrl+b % = vertical split
ctrl+b " = horizontal split
ctrl+b o = switch panes
ctrl+b ! = convert pane to window
ctrl+b <arrow> = resize pane
ctrl+b : kill-pane = close pane
ctrl+b : set mouse on = avail mouse buttons and scrolling
ctrl+b & = close window
```

#### change tmux config file (.tmux.conf) to make panes in same dir and making the mouse usable.
```bash
bind '"' split-window -c "#{pane_current_path}"
bind '%' split-window -h -c "#{pane_current_path}"
set-option -g mouse on
```

#### tmux session management
_to detach from a session hit_: ctrl+b, d
```bash
tmux new-session -s mysession
tmux ls
tmux attach-session -t mysession
tmux kill-session -t mysession
```

#### command for clearing history
```bash
[Command]
Command="
    copyq:
    tab(config('clipboard_tab'))
    var count = size()
    if (count) {
      items = Array
        .apply(0, Array(count))
        .map(function(x,i){return i})
      remove.apply(this, items)
    }
    popup('Clipboard Tab Cleared')"
GlobalShortcut=meta+ctrl+x
Icon=\xf2ed
IsGlobalShortcut=true
Name=Clear Clipboard Tab
```

## create partition using gparted

## taskmanager cuda graph
Grafana + Prometheus + Node Exporter + DCGM Exporter


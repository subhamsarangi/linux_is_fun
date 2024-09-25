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

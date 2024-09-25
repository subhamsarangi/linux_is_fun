# SOFTWARES

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


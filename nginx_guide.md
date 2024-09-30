# NGINX
To set up Nginx on Ubuntu and create a server configuration, follow these steps:

### Installation

1. **Update the package list:**
   ```bash
   sudo apt update
   ```

2. **Install Nginx:**
   ```bash
   sudo apt install nginx
   ```

3. **Start and enable Nginx:**
   ```bash
   sudo systemctl start nginx
   sudo systemctl enable nginx
   ```

### Create a Server Configuration

1. **Navigate to the Nginx configuration directory:**
   ```bash
   cd /etc/nginx/sites-available/
   ```

2. **Create a new configuration file (e.g., `my_site`):**
   ```bash
   sudo nano my_site
   ```

3. **Add your server block configuration (the examples provided below) ⬇️ **

4. **Save and exit the editor.**

5. **Create a symbolic link to enable the site:**
   ```bash
   sudo ln -s /etc/nginx/sites-available/my_site /etc/nginx/sites-enabled/
   ```

### Test and Restart Nginx

1. **Test the configuration for syntax errors:**
   ```bash
   sudo nginx -t
   ```

2. **Restart Nginx to apply changes:**
   ```bash
   sudo systemctl restart nginx
   ```
   
### A simple example
The following configuration serves a static file from the specified directory when accessed via the given IP address.

```nginx
server {
    listen 80;
    server_name 192.168.1.190;

    root /var/www/my_site;
    index index.html;

    location / {
        try_files $uri $uri/ =404;
    }
}
```

- **listen 80;**: The server listens for incoming requests on port 80.
- **server_name 192.168.1.190;**: This specifies the server's name or IP address that it responds to.
- **root /var/www/my_site;**: The root directory for serving files is set to `/var/www/my_site`.
- **index index.html;**: The default file to serve when accessing the root directory is `index.html`.
- **location / { ... }**: This block handles requests for the root URL.
  - **try_files $uri $uri/ =404;**: It attempts to serve the requested file (`$uri`) or directory (`$uri/`). If neither exists, it returns a 404 error.


### another example
```nginx
server {
    listen 80;
    server_name 192.168.1.190;

    location /files/ {
        alias /var/www/my_site/files/;
        autoindex on;
        autoindex_exact_size off;  # Optional
        autoindex_localtime on;    # Optional
    }
}
```
This configuration allows users to browse and view files located in `/var/www/my_site/files/` through the web server.

- **location /files/**: This block applies to requests that start with `/files/`.
- **alias /var/www/my_site/files/**: It maps the `/files/` URL to the filesystem directory `/var/www/my_site/files/`.
- **autoindex on;**: Enables directory listing, allowing users to see the files in that directory if no specific file is requested.
- **autoindex_exact_size off;**: Displays human-readable file sizes instead of exact byte counts.
- **autoindex_localtime on;**: Shows file timestamps in the server's local timezone.

### yet another example
To serve the files directly from the root of your server (i.e., accessing them via http://192.168.1.190/), the configuration should be
```nginx
server {
    listen 80;
    server_name 192.168.1.190;

    root /var/www/my_site/files;

    location / {
        try_files $uri $uri/ =404;
    }

    autoindex on;
}
```

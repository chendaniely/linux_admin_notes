- Use systemd to start it up `systemctl start nginx`
    - Make sure you disable Appache: `systemctl disable --now httpd` `systemctl stop httpd`
- Default web server root: `/usr/share/nginx/html`
- Default configuration file: `/etc/nginx/conf.d/default.conf`
    - Additional server block(virtual hosts): `/etc/nginx/conf.d`
    - In CentOS you can use `rpm -qc nginx` to look at where the configuration files are stored
    - `default.d` and `conf.d` directories can be used to store additional server blocks
 - Within a configuration file
    - You can see where the root web page is
    - and where you can put in certificates

- `/usr/share/nginx/html/`
    - `index.html`: the default webpage
    - `systemctl start nginx` to start nginx

- Setting up selinux
    - `semanage fcontext -a -t httpd_sys_content_t "/www(.*)?"`
        - where `/www` is where you would put a 'new' server root
    - `restorecon -Rv /www`

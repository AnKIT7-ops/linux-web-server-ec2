# Linux & Nginx Commands

## System Information

```bash
whoami
hostname
pwd
uname -a
hostname -I
free -h
df -h
uptime
```

## Files and Directories

```bash
ls
ls -la
cd /
cd ~
mkdir linux-practice
touch test.txt
cat test.txt
```

## File Operations

```bash
echo "Hello from my EC2 server" > test.txt
echo "Linux Web Server Project" >> test.txt
```

`>` overwrites a file.  
`>>` appends to a file.

## Networking

```bash
ip addr
ip route
hostname -I
ping -c 4 google.com
curl http://localhost
curl -I https://google.com
```

## Ports

```bash
sudo ss -tulpn
sudo ss -tulpn | grep :80
```

Important ports:

```text
22  -> SSH
80  -> HTTP
443 -> HTTPS
```

## Processes

```bash
ps aux
top
```

Press `q` to exit `top`.

## Nginx Installation

```bash
sudo apt update
sudo apt install nginx -y
```

## Nginx Service Management

```bash
sudo systemctl start nginx
sudo systemctl stop nginx
sudo systemctl restart nginx
sudo systemctl reload nginx
sudo systemctl status nginx
sudo systemctl enable nginx
```

## Nginx Configuration

```bash
sudo nginx -t
sudo ls /etc/nginx
sudo ls /etc/nginx/sites-enabled
sudo cat /etc/nginx/sites-enabled/default
```

Website root:

```text
/var/www/html
```

## Nginx Logs

```bash
sudo tail -n 20 /var/log/nginx/access.log
sudo tail -n 20 /var/log/nginx/error.log
sudo tail -f /var/log/nginx/access.log
```

Press `Ctrl+C` to stop following a log.

## Website

```bash
ls -la /var/www/html
cat /var/www/html/index.html
curl http://localhost
```

## Troubleshooting

```bash
sudo systemctl status nginx
sudo ss -tulpn | grep :80
curl http://localhost
sudo nginx -t
ls -la /var/www/html
sudo tail -n 20 /var/log/nginx/error.log
```

## Troubleshooting Workflow

```text
Website not working
        |
        v
Check EC2 state
        |
        v
Check Security Group
        |
        v
Check Nginx status
        |
        v
Check port 80
        |
        v
Check website files
        |
        v
Check Nginx configuration
        |
        v
Check logs
```

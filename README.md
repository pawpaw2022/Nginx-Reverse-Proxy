# Nginx-Reverse-Proxy

# 使用NGINX进行反向代理 生产镜像网站

## 1. 获取域名+云服务器IP
- 首先需要获取你的云服务器的IP地址，并且注册一个域名。域名注册后，将域名解析指向你的云服务器IP地址。

## 2. 注册IP 至 域名DNS 
- 在你的域名注册商的控制面板中，找到DNS管理页面，添加一条A记录，将域名解析到你的云服务器IP地址。

## 3. 生产TLS 证书
- 为了实现HTTPS协议访问，需要为你的域名生成TLS证书。可以使用Certbot工具来自动完成证书生成和配置。

```bash
sudo apt update
sudo apt install certbot python3-certbot-nginx
sudo certbot --nginx -d your_domain
```

## 4. 编写NGINX配置文件
- 安装NGINX并配置反向代理的相关设置。
  
```
sudo apt install nginx
sudo vi /etc/nginx/nginx.conf
```

- 在nginx.conf中配置反向代理相关的内容，然后重新加载NGINX服务使配置生效。

```
sudo systemctl reload nginx.service
sudo systemctl start nginx.service
```

- 可以使用以下命令检查NGINX服务的状态：
  
```
sudo systemctl status nginx.service
```




# 部署指南

## 生产环境构建

1. 执行构建命令：

```bash
npm run build
```

2. 构建产物将生成在`dist`目录下

## Nginx 配置示例

```nginx
server {
    listen       80;
    server_name  manage.leyou.com;

    location / {
        root   /usr/share/nginx/html/leyou-manage;
        index  index.html index.htm;
        try_files $uri $uri/ /index.html;
    }

    location /api {
        proxy_pass http://127.0.0.1:8081;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
    }
}
```

## 部署注意事项

1. 确保服务器已安装 Nginx
2. 静态资源需要配置正确的 MIME 类型
3. 跨域问题需通过 Nginx 反向代理解决
4. 建议启用 Gzip 压缩提升性能

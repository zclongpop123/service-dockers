使用说明
===

- 安装 docker + docker-compose
  
  参考方法 https://github.com/zclongpop123/chinese-mirrors/blob/main/docker-ce.md

- 自己创建或者下载本仓库里的docke-compose.yml, 选择修改docker-compose.yaml里对应的域名
  ```bash
  git clone https://github.com/zclongpop123/service-dockers.git
  ```

- 运行镜像服务
  ```bash
  cd service-dockers && docker-compose up -d
  ```
  
 - 所有服务的数据默认挂载的 /home 下面的各自文件夹内，并且会自动生成。
   ```
   /home
      ├── nginx
      ├── portainer
      ├── postgresql
      ├── confluence
      ├── gitlab
      └── ...
   ```
   如果 confluence 或者 jira 启动失败，需要修改一下home下面对应文件夹的属主和属组，然后重启服务。
   ```bash
   chown -R 2002:2002 /home/confluence 
   ```
 
 - 一些网页服务默认关闭里端口映射，通过 Nginx 转发过去，conf.d 为Nginx的配置，需要手动拷贝过去，conf.d 里的二级域名，然后重启Nginx或者重新加载Nginx配置
   ```bash
   docker-compose restart nginx
   ```
   或者
   ```bash
   nginx -s reload
   ```
 

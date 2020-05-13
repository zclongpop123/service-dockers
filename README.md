How To Use
===

- 安装 docker
  ```bash
  yum install docker -y
  
  systemctl enable docker.service && systemctl start docker.service
  ```

- 安装 docker-compose

  最新发布地址 https://github.com/docker/compose/releases

  ```bash
  sudo curl -L https://github.com/docker/compose/releases/download/1.25.4/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose

  sudo chmod +x /usr/local/bin/docker-compose

  sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
  ```

- 检查 docker-compose

  ```bash
  docker-compose --version
  ```

- 自己创建或者下载本仓库里的docke-compose.yml

- 运行镜像服务
  ```bash
  docker-compose up -d
  ```
  
 - 所有服务的数据默认挂载的 /home 下面的各自文件夹内。
   ```
   /home
      ├── confluence
      ├── gitlab
      ├── lost+found
      ├── nginx
      ├── pipeline
      ├── portainer
      └── postgresql
   ```
 
 - 一些网页服务默认关闭里端口映射，通过 Nginx 转发过去。
 - 使用时需要根据个人需求，修改docker-compose 和 conf.d 里的二级域名。

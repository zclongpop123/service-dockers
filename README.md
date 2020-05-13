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

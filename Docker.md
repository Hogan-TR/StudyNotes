1. 从 Docker 镜像仓库获取镜像

   ```bash
   docker pull [选项] [Docker Registry 地址[:端口号]/]仓库名[:标签]
   
   Ex:
   $ docker pull ubuntu:18.04
   18.04: Pulling from library/ubuntu
   bf5d46315322: Pull complete
   9f13e0ac480c: Pull complete
   e8988b5b3097: Pull complete
   40af181810e7: Pull complete
   e6f7c7e5c03e: Pull complete
   Digest: sha256:147913621d9cdea08853f6ba9116c2e27a3ceffecf3b492983ae97c3d643fbbe
   Status: Downloaded newer image for ubuntu:18.04
   ```

2. 启动并运行一个容器

   ```bash
   $ docker run -it --rm \
       ubuntu:18.04 \
       bash
   
   root@e7009c6ce357:/# cat /etc/os-release
   NAME="Ubuntu"
   VERSION="18.04.1 LTS (Bionic Beaver)"
   ID=ubuntu
   ID_LIKE=debian
   PRETTY_NAME="Ubuntu 18.04.1 LTS"
   VERSION_ID="18.04"
   HOME_URL="https://www.ubuntu.com/"
   SUPPORT_URL="https://help.ubuntu.com/"
   BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
   PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
   VERSION_CODENAME=bionic
   UBUNTU_CODENAME=bionic
   ```

   - `-it` :  两个参数，一个是 `-i`：交互式操作，一个是 `-t` 终端 
   - `--rm` : 容器退出后随之将其删除
   - `bash`：放在镜像名后的是 **命令**，这里希望有个交互式 Shell，因此用的是 `bash`
   - `exit` : 退出容器

3. 列出镜像 (只显示顶层镜像)

   ```bash
   $ docker image ls
   $ docker image ls -a              # 显示包括中间层镜像的所有镜像
   $ docker image ls ubuntu          # 列出部分镜像
   ```

4. 查看镜像、容器、数据卷所占用的空间

   ```bash
   $ docker system df
   ```

5. 删除镜像

   ```bash
   $ docker image prune              # 虚拟镜像
   ```

6. 删除本地镜像

   ```bash
   $ docker image rm [选项] <镜像1> [<镜像2> ...]
   ```

7. Loading ...




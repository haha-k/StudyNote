### docker

docker build


DOCKFILE

1. `FROM xxxx`
* 指定基础镜像，以该镜像为第一层，在这一层上面进行定制
* scratch #不易任何镜像为基础，接下来的指令来作为第一层镜像

---
2. `RUN <命令>/["可执行文件","参数1","参数2"]`
* 每个指令都会新建立一层镜像，所以应该用类似格式
```shell
    RUN buildDeps='gcc libc6-dev make wget' \
        && apt-get update \
        && apt-get install -y $buildDeps \
        ...
        && apt-get purge -y --auto-remove $buildDeps
```
* 镜像构建时，一定要确保每一层只添加真正需要添加的东西，任何无关的东西都应该清理掉。

3.COPY
* `COPY [--chown=<user>:<group>] <源路径>... <目标路径>`
* `COPY [--chown=<user>:<group>] ["<源路径1>",... "<目标路径>"]`
## docker_yapi
使用 Docker 本地部署——YApi-高效、易用、功能强大的可视化接口管理平台

### 命令

1. 启动服务 
```sh
#在当前目录下执行以下命令
$docker-compose up -d
```
2. 卸载服务 
```sh
#在当前目录下执行以下命令
$docker-compose down
```
3. 查询 volume
```sh
$docker volume ls
DRIVER    VOLUME NAME
local     d3c24f4a36156f4cb410c4634dbfd496770830930d1f25357a9147bec7bdae73
local     docker_yapi_mongodata
```
4. 备份数据
```sh
# windows下执行
$docker run --volumes-from mongo-yapi -v c:\backup:/backup ubuntu tar cvf /backup/backup.tar -C /data/db .
# mac下执行
$docker run --volumes-from mongo-yapi -v /Users/project/aboutdocker/backup/yapi:/backup ubuntu tar -cvf /backup/backup.tar /data/db

```
5. 还原数据
```sh
# windows下执行
$docker run --volumes-from mongo-yapi -v c:\backup:/backup ubuntu bash -c "cd /data/db && tar xvf /backup/backup.tar -C /data/db "
# mac下执行
$docker run --volumes-from mongo-yapi -v /Users/project/aboutdocker/backup/yapi:/backup ubuntu tar -xvf /backup/backup.tar -C /
```
6. 删除卷
```sh
# 删除指定卷
$docker volume rm docker_yapi_mongodata
# 删除所有没有被使用的卷
$docker volume prune 
```
7. ddd

### 资源

#### 参考
- [https://ducafecat.tech/2020/05/21/docker/docker-01-install-yapi/](https://ducafecat.tech/2020/05/21/docker/docker-01-install-yapi/)
- [https://github.com/fjc0k/docker-YApi](https://github.com/fjc0k/docker-YApi)
- [https://docs.docker.com/storage/volumes/#backup-restore-or-migrate-data-volumes](https://docs.docker.com/storage/volumes/#backup-restore-or-migrate-data-volumes)

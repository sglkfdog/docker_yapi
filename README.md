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
local     5d1a10e5be31eba8a1cfd02790f83fc26fc2f49e6bd2c55d3559023e22bfd081
local     30dd00e803a2d64f9d2cce268a07fb39f2a4ad4054c9598844dd3db4b232166e
local     44ae4240fe9554a2cce9f06735440b2bbf0d067ad3a7964df782a653a2363e22
local     63defa1d3080b8997b360b1e940bb3663ae4905ea4a4045fd0388678c2ed9aa0
local     d3c24f4a36156f4cb410c4634dbfd496770830930d1f25357a9147bec7bdae73
local     docker_yapi_mongo-data
```
4. 备份数据
```sh
# windows下执行
$docker run --rm --volumes-from mongo-yapi -v c:\backup:/backup ubuntu tar cvf /backup/backup.tar -C /data/db .
# mac下执行
$docker run --rm --volumes-from mongo-yapi -v /Users/project/aboutdocker/backup/yapi:/backup ubuntu tar cvf /backup/backup.tar -C /data/db .

```
5. 还原数据
```sh
# windows下执行
$docker run --rm --volumes-from mongo-yapi -v c:\backup:/backup ubuntu bash -c "cd /data/db && tar xvf /backup/backup.tar -C /data/db "
# mac下执行
$docker run --rm --volumes-from mongo-yapi -v /Users/project/aboutdocker/backup/yapi:/backup ubuntu bash -c "cd /data/db && tar xvf /backup/backup.tar -C /data/db "
```
6. dd

### 资源

#### 参考
- [https://ducafecat.tech/2020/05/21/docker/docker-01-install-yapi/](https://ducafecat.tech/2020/05/21/docker/docker-01-install-yapi/)
- [https://github.com/fjc0k/docker-YApi](https://github.com/fjc0k/docker-YApi)
- [https://docs.docker.com/storage/volumes/#backup-restore-or-migrate-data-volumes](https://docs.docker.com/storage/volumes/#backup-restore-or-migrate-data-volumes)

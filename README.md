## 👋 Welcome to stikked 🚀  

stikked README  
  
  
## Install my system scripts  

```shell
 sudo bash -c "$(curl -q -LSsf "https://github.com/systemmgr/installer/raw/main/install.sh")"
 sudo systemmgr --config && sudo systemmgr install scripts  
```
  
## Automatic install/update  
  
```shell
dockermgr update stikked
```
  
## Install and run container
  
```shell
mkdir -p "$HOME/.local/share/srv/docker/stikked/rootfs"
git clone "https://github.com/dockermgr/stikked" "$HOME/.local/share/CasjaysDev/dockermgr/stikked"
cp -Rfva "$HOME/.local/share/CasjaysDev/dockermgr/stikked/rootfs/." "$HOME/.local/share/srv/docker/stikked/rootfs/"
docker run -d \
--restart always \
--privileged \
--name casjaysdevdocker-stikked \
--hostname stikked \
-e TZ=${TIMEZONE:-America/New_York} \
-v "$HOME/.local/share/srv/docker/casjaysdevdocker-stikked/rootfs/data:/data:z" \
-v "$HOME/.local/share/srv/docker/casjaysdevdocker-stikked/rootfs/config:/config:z" \
-p 80:80 \
casjaysdevdocker/stikked:latest
```
  
## via docker-compose  
  
```yaml
version: "2"
services:
  ProjectName:
    image: casjaysdevdocker/stikked
    container_name: casjaysdevdocker-stikked
    environment:
      - TZ=America/New_York
      - HOSTNAME=stikked
    volumes:
      - "$HOME/.local/share/srv/docker/casjaysdevdocker-stikked/rootfs/data:/data:z"
      - "$HOME/.local/share/srv/docker/casjaysdevdocker-stikked/rootfs/config:/config:z"
    ports:
      - 80:80
    restart: always
```
  
## Get source files  
  
```shell
dockermgr download src casjaysdevdocker/stikked
```
  
OR
  
```shell
git clone "https://github.com/casjaysdevdocker/stikked" "$HOME/Projects/github/casjaysdevdocker/stikked"
```
  
## Build container  
  
```shell
cd "$HOME/Projects/github/casjaysdevdocker/stikked"
buildx 
```
  
## Authors  
  
🤖 casjay: [Github](https://github.com/casjay) 🤖  
⛵ casjaysdevdocker: [Github](https://github.com/casjaysdevdocker) [Docker](https://hub.docker.com/u/casjaysdevdocker) ⛵  

# docker-exe1
# commandes à exécuter
```shell
docker run -it -v /MountPoint --name myalpes alpine /bin/ash
docker start myalpes
docker attach myalpes
cat > test.py
"WARNING: ret pointer is null"
docker commit myalpes myalpine:v12
docker save -o myfile.tar myalpine:v12
docker rmi -f $(docker images -q)
cat myfile.tar | docker import - myalpine:v12
docker history myalpine:v12
docker login -u <docker_hub_account> -p <password>
docker image tag myalpine:v12 <docker_hub_account>/myalpine:v12
docker push <docker_hub_account>/myfirstimage
```

## EXERCICE 1
Creez un repo github nommé **docker-exe1**  
il doit etre public, avec un fichier README.md , un fichier  .gitignore valable pour le langage Python, une License MIT  
Faites un git clone dans votre directory project local   
mettre en place dans goland la connexion ssh vers votre VM   
attention a ne pas oublier le mapping sur le deployment path sur /home/ubuntu/docker-exe1  
Mettre les commandes de l'exercice suivant dans le fichier README.md

Dans une commande docker run
* vous devez etre en interactif et avec un tty pour le display
* le container doit etre nommé **myalpes**
* dans cette commande creer un volume /MountPoint
* image doit etre alpine
* passer la commande /bin/ash   
  Ensuite a l'interieur du container
* creer un fichier test.py
* et inserez le texte "WARNING: ret pointer is null"
---
* a partir de ce container créer une image nommée  myalpine:v12.
* Supprimer les metadata de cette image avec docker export et docker import
* Verifier avec docker history
* mettez cette image dans docker hub sous votre compte docker hub

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

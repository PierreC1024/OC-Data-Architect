# Projet 2 : Réalisez un apprentissage distribué

## 1. Download images

## 2. Éxécuter le script sur une image docker

### Créer l'image docker 

```bash
docker build -t realiser-app-distrib:test .
```

### Lancer le container docker en synchronisant un volume avec les fichiers locaux
```bash
docker run --mount type=bind,source="$(pwd)"/,target=/srv  -it realiser-app-distrib:test /bin/bash
> python3 process.py
```

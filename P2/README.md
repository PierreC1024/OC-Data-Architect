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

### Éxécuter un script au démarrage d'un cluster EMR

1. Créer un script shell (`emr-init-script.sh` présent dans ce repo). 

2. Le charger sur un bucket S3.

3. Créer un cluster EMR, aller dans les options avancées, dans la step3, dans la rubrique "Additional Options", Ajouter une nouvelle "Custom Action" dans Bootstrap Action. Spécifier alors le lien S3 de votre script. 

4. Sur la page de votre cluster, vous remarquerez une nouvelle section `Bootstrap Actions` avec votre script. Une fois le cluster prêt, le script a été éxecuter. 

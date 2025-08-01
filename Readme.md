# Formation Linux


## Système de fichiers

### Déplacement
```
cd : changement de répertoire
ls : listing
pwd : où suis je ?

cd                   # chez moi
cd /var/log/apt      # chemin absolu
cd Images/Photos     # chemin relatif (répertoire courant = pwd)
cd ./Images/Photos   #     idem
ls ~/Bureau          # chemin relatif au répertoire maison (home directory)
cd ..                # remonte au repertoire parent
```

### Contenu de fichier
```
cat         # visualiser le fichier en entier
more        # idem + défiler
less        # idem + défiler : bidirectionnel, recherche (/)
head        # début de fichier (utiliser -3 pour les 3 premières)
tail        # fin de fichier (utiliser -3 pour les 3 dernières)

tail -500 history.log  | less
```

### Nature/Type de fichier
```
file history.log
file history.log.gz
file /usr/bin/tree
```

### Traitement de fichier ou résultat de commande (|)
```
wc -l       # compter les lignes
sort        # trier : -n (numerique)
grep        # filtrer
find        # recherche en profondeur
cut         # chercher une colonne dans un fichier type csv (séparateur)

ls /usr/bin | wc -l          # compter le nombre de fichiers du répertoire /usr/bin
ls /usr/bin | grep tree      # filtrer les fichiers contenant 'tree' du répertoire /usr/bin
```

### Copie, déplacer, renommer, suppression
```
cp : copy (copie + renomme)
mv : move (déplacement, renomme)

rm : remove (supprimer)
rm un_fichier
rm un_dossier -rf
```

# Affichage, écriture écran

```
echo Bonjour
echo "Bonjour tout le monde"
echo $SHELL
echo "Mon shell est : $SHELL"
```

## Utilisateurs
```
id              # fiche d'identité (défaut soi même)
id matthias     # idem sur qqn d'autre

whoami          # qui suis je
```

## Processus
```
ps                      # lister les processus
ps -aux                 # lister tous les processus
ps -aef                 # lister tous les processus (autre affichage)

pstree                  # arborescence des processus
```

## Services
```
systemctl status            # tous les services

systemctl status nginx      # le service nginx
systemctl stop nginx
systemctl start nginx
```

## Réseau
```
ip a                # liste des interfaces réseaux et IP attribuées

ss -plantu          # processus en mode écoute, connexions établies
netstat -plantu     # idem
```

## Travail à distance
NB: auparavant mise en place de clé SSH.
```
ssh user@nom-machine            # connexion à distance par nom de machine avec tel utilisateur
ssh user@10.10.125.3            # par IP
ssh -l user nom_machine_ou_ip   # idem

ssh user@nom-machine commande_distante    # executer une commande à distance

scp fichier_local user@nom-machine:/tmp     # copier le fichier local dans le répertoire /tmp distant
```

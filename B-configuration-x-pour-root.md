# Connexion X et utilisateur Root

## Installation du client X

### Sur la machine cliente (hôte physique)

Vous devez installer VCXSRV sur votre hôte pour pouvoir afficher les différentes applications graphiques de votre machine virtuelle.

Configurer Putty pour autoriser le `X11-forwarding`

### Sur la machine virtuelle
On installe le paquet `x11-apps` et on lance `xeyes` ou `xclock`.

Une fenêtre devrait apparaître


## Blocage avec root
On a parfois ce message quand on exécute un programme avec `sudo`

```
X11 connection rejected because of wrong authentication.
```


### Solution

Pour corriger le problème il faut:

1. lancer la commande suivante et en copier la sortie dans le presse-papier:

```bash
$ xauth list
netservice/unix:10  MIT-MAGIC-COOKIE-1  9577b0ac5ac9e8cdb6a96e7b53f6969a
$
```

2. se connecter en tant que `root` (`sudo su -`) puis faire un `xauth add` en collant le contenu du presse-papier à la suite:

```bash
$ xauth add netservice/unix:10  MIT-MAGIC-COOKIE-1  9577b0ac5ac9e8cdb6a96e7b53f6969a
$
```

Le chiffre `10` de la chaîne `netservice/unix:10` correspond au numéro du DISPLAY. DISPLAY est une variable d'environnement qui permet aux applications d'afficher leur interface graphique.

Pour connaitre la valeur de cette variable, taper:

```bash
$ echo $DISPLAY
localhost:10.0
```

Le chiffre juste après le `:` (*10*) correspond ici au chiffre affiché sur la ligne du cookie: `netservice/unix:`*10*`  MIT-MAGIC-COOKIE-1  9577b0ac5ac9e8cdb6a96e7b53f6969a`

Si vous lancez plusieurs sessions différentes, votre DISPLAY aura une valeur différente: à vérifier...

3. Tester:

```bash
sudo xeyes
```



## Automatisation
Voici la solution pour automatiser: un script qui transfère les autorisations à root.

Ce script peut être ajouté à la fin de votre fichier `.bash_profile` sur votre serveur.

### Scripts



Pour cela, vous avez deux versions du  scripts ci-dessous.

Ce script doit être sauvé dans un fichier `xforward2root`. Le fichier doit être rendu exécutable grâce à la commande `chmod +x`.

Il pourra être exécuté en lançant la commande `./xforward2root`

#### Première version
```
#!/bin/bash
#shebang

#première méthode
#Je récupère le cookie (qui est stocké dans mon .Xauthority dans mon HOME)
#"mon" == pour l'utilisateur courant
cookie=`xauth list |grep :$(echo $DISPLAY | cut -d : -f 2 | cut -d . -f 1) `
#Le guillement inversé ` c'est altgr-7
echo $cookie

#J'exécute en tant que root la commande suivante:
#sudo xauth add $cookie #Ne marche pas dans certains cas (Trisquel)
sudo su <<EOF
xauth add $cookie
EOF

#qui a pour effet d'ajouter le cookie récupéré précédemment dans le fichier
#.Xauthority qui se trouve dans le HOME de root
```


#### Deuxième version
```
#!/bin/bash

#deuxième méthode
numdisplay=$(echo $DISPLAY | cut -d: -f2 | cut -d. -f1)
cookie=$(xauth list |grep :$numdisplay)
sudo xauth add $cookie
#sudo xauth add $cookie #Ne marche pas dans certains cas (Trisquel)
sudo su <<EOF
xauth add $cookie
EOF
```

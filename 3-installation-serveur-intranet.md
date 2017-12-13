# Installation d'un Dokuwiki

## Installation Apache

Installation d'un serveur Apache

Vous allez installer un **virtual host** qui gère le site monserveur.example.com

Il affichera un fichier `index.html` par défaut.

C'est un fichier texte qui contiendra les lignes suivantes:

```html
<!doctype html>
<html>
  <head>
		<meta http-equiv="Content-type" content="text/html; charset=utf-8">
		<META HTTP-EQUIV="CACHE-CONTROL" CONTENT="NO-CACHE">

  </head>
<body>

	<div id="container">
		<h1>Titre du paragraphe</h1>
    Du texte dans le paragraphe
	</div>

</body>
</html>
```

Vous allez devoir placer ce document dans le `DocumentRoot` de votre VirtualHost Apache.

Tous ces mots vous sont inconnus ? Vous allez découvrir à quoi ils correspondent

Vous allez modifier votre DNS pour qu'il fasse pointer l'adresse
` monserveur.example.com` vers la VM qui héberge le serveur Apache.

Vous pourrez tester en utilisant votre navigateur en allant à l'adresse: http://monserveur.example.com

### Installation d'Apache

Cette partie se fera avec l'aide du formateur

Pour les plus pressé.e.s, il est possible de consulter cet article:

http://siguillaume.developpez.com/tutoriels/apache/installation-configuration-serveur-web-apache/

### Installation d'un VirtualHost

Vous pouvez utiliser ce tutoriel pour faire ce qui a été décrit précédemment.

https://doc.ubuntu-fr.org/tutoriel/virtualhosts_avec_apache2


## Installation dokuwiki

Installer *dokuwiki*

créer un **virtual host** qui gère `wiki.example.com`

Modifier votre DNS pour que le wiki soit accessible sur cette URL.

Vous allez installer le module markdowku (Markdown pour Dokuwiki)

Vous allez étudier la syntaxe Markdown et l'utiliser (voir https://daringfireball.net/projects/markdown/syntax.php/)

# L'incontournable création d'un blog

Merci d'essayer Lithium! Ce guide est pour les développeurs PHP qui cherchent à se faire une idée de ce que peut faire Lithium, et à quoi ressemble le développement d'une application web avec ce framework. Mettre la main à la pâte et créer une application simple est un bon moyen pour pendre la température et savoir à quoi ressemble le développement rapide d'applications, façon Lithium.

## Préparation du terrain

La première chose à faire est d'obtenir une copie récente de Lithium. Si cela n'est pas encore fait, jetez un oeil au guide [Démarrage rapide](http://lithify.me/docs/manual/getting-started/installation.wiki). Suivez minutieusement chaque étape de ce guide.

Une fois Lithium prêt, nous avons besoin d'une couche de persistance des données. Traditionnellement, cela est fait en utilisant une base de données SQL, comme MySQL. Pour cet exemple cependant, nous allons utiliser quelque chose de différent: MongoDB. Utiliser une installation différente montre la flexibilité du framework quant à l'utilisation de moteurs différents.

MongoDB est une solution hybride, faite à partir des bonnes choses des bases de données clé/valeur et des systèmes traditionnels SGBDR. L'installation est rapide et facile.

La meilleure façon de commencer est de télécharger un binaire à partir du site web MongoDB. Vérifiez leur [page de téléchargement] (http://www.mongodb.org/display/DOCS/Downloads), et cherchez le binaire qui correspond à votre plate-forme.

Ensuite, un peu de configuration en créant un répertoire de données pour Mongo. Pour ce faire, crééz un répertoire `/data/db` sur votre système (`C:\data\db` pour nos amis sur Windows).

Enfin, démarrez la base de données. Lancez `/chemin/vers/mongodb/bin/mongod`, et attendez la fin de l'affichage des informations d'initialisation. Si vous rencontrez des problèmes en cours de route, le [guide de démarrage] MongoDB (http://www.mongodb.org/display/DOCS/Getting+Started) est un bon endroit pour obtenir de l'aide.

Pour MongoDB + PHP, vous aurez besoin d'installer le module PECL Mongo. Pour la plupart des systèmes ([sauf Windows](http://www.mongodb.org/display/DOCS/Installing+the+PHP+Driver#InstallingthePHPDriver-WindowsInstall)), c'est aussi simple que:

	sudo pecl install mongo

Une fois l'installation terminée avec succès, n'oubliez pas d'ajouter la ligne `extension=mongo.so` à votre fichier `php.ini`.

Une dernière chose: une meilleure gestion des erreurs et de paramètre debug/production est prévue pour une prochaine version. Jusque-là, vous devrez allez vous même au fichier `/app/config/bootstrap.php` pour faire vos propres décisions d'affichage des erreurs. Pour l'instant, je vous suggère de permettre l'affichage des erreurs pour votre installation de PHP ou en utilisant `ini_set ()` pour l'activer temporairement pendant que nous développons.

	ini_set("display_errors", 1);

## Configuration Setup

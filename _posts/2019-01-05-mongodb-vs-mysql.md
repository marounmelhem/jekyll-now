---
published: true
---
_Selon la documentation officielle de MongoDB_

> _MongoDB est une base de données de documents dotée de l’évolutivité et de la flexibilité souhaitées pour les requêtes et l’indexation dont vous avez besoin._


**Comment fonctionne MongoDB?**

> _MongoDB stocke les données dans des documents flexibles de type JSON, ce qui signifie que les champs peuvent varier d'un document à l'autre et que la structure des données peut être modifiée au fil du temps._


**Quelles sont les alternatives?**

Lors du choix d'une base de données pour votre projet, l'une des décisions les plus importantes et les plus importantes est de choisir une structure de données relationnelle (SQL) ou non relationnelle (noSQL).

Bien que les deux options permettent de faire le travail, il existe de nombreuses différences clés que chaque développeur doit garder à l'esprit.


**De quoi on va parler?**

- Quels sont les avantages d'utiliser MongoDB?
- Comment configurer MongoDB sur Ubuntu 16.04 (en utilisant php)
- Les outils MongoDB à utiliser
- Parlons de MySQL
- MongoDB vs MySQL
- Exemple de codage MongoDB / MySQL


## Quels sont les avantages d'utiliser MongoDB?

**MongoDB schema less nature**

MongoDB est une base de données de documents dans laquelle une collection contient différents documents. Le nombre de champs, le contenu et la taille du document peuvent différer d'un document à l'autre.


**Facilité d'évolution**

Contrairement aux bases de données SGBDR, MongoDB est facile à mettre à l'échelle car il nécessite beaucoup moins de ressources.


**La structure d'un seul objet est claire.**

**Aucune jointure complexe.**

**Capacité de requête profonde. MongoDB prend en charge les requêtes dynamiques sur des documents en utilisant un langage de requête basé sur les documents presque aussi puissant que SQL.**

**Utilise la mémoire interne pour stocker le groupe de travail (fenêtré), permettant un accès plus rapide aux données.**


## Comment configurer MongoDB sur Ubuntu 16.04 (en utilisant php)

**Connexion via ssh**

![1.png](http://c1.maroun.xyz/github_screenshots/1.png)


**Créer un dossier de site et configurer les autorisations**

![3.png](http://c1.maroun.xyz/github_screenshots/3.png)


**Créer un site conf dans /etc/apache2/sites-available**

![5.png](http://c1.maroun.xyz/github_screenshots/5.png)


**Activer le site dans /etc/apache2/sites-available**

![7.png](http://c1.maroun.xyz/github_screenshots/7.png)


**Mise à jour des packages**

```
sudo apt update
```

**Installer MongoDB**

```
sudo apt install -y mongodb
```

**Vérification du service et de la base de données**

```
sudo systemctl status mongodb
```

**Démarrer MongoDB**

```
sudo systemctl start mongodb
```

**Redémarrage de MongoDB**

```
sudo systemctl restart mongodb
```

**Arrêt de MongoDB**

```
sudo systemctl stop mongodb
```

**Installer l'extension MongoDB php**

```
sudo apt-get install php-mongodb
```

**Installer MongoDB si php est déjà installé**

```
sudo apt install php7.2-mongodb
sudo pecl install mongodb
sudo bash
sudo echo "extension=mongodb.so" >> /etc/php/7.2/apache2/php.ini
```

**Installer MongoDB si php n'est pas installé**

```
sudo apt-get install software-properties-common
sudo add-apt-repository ppa:ondrej/php
sudo apt update
sudo apt install php7.2 libapache2-mod-php7.2 php7.2-common php-7.2-cli php7.2-mongodb php-pear php7.2-dev
```

![10.png](http://c1.maroun.xyz/github_screenshots/10.png)

**Redémarrer apache2**

```
sudo apachectl restart
```

**Vérifiez l'installation de MongoDB en ajoutant un fichier phpinfo**

```
sudo vim /var/www/html/info.php
```

**Ajouter la fonction phpinfo**

```
<?php
phpinfo();
?>
```

**Enregistrer le fichier créé ": x!" commander**
![11.png](http://c1.maroun.xyz/github_screenshots/11.png)


**Vérifier l'installation de MongoDB à partir de phpinfo (website.com/info.php)**
![12.png](http://c1.maroun.xyz/github_screenshots/12.png)


**Installer MongoDB (pour les utilisateurs Mac OSX)**

Si vous n'avez pas installé de bière, vous devriez:
https://brew.sh/

```
brew update
brew install mongodb
```

## Les outils MongoDB à utiliser

Si vous utilisez habituellement MySQL, vous connaissez probablement des outils tels que __phpmyadmin__. C'est le moyen le plus simple de gérer les données MySQL sur le serveur.

Eh bien, pour MongoDB, il existe un outil appelé RoboMongo et voici comment vous l'installez:

```
wget https://download.robomongo.org/0.8.5/linux/robomongo-0.8.5-x86_64.deb
```
```
sudo dpkg -i robomongo-0.8.5-x86_64.deb
```
```
robomongo
```

__NB:__
__-MongoDB est disponible pour Linux, MacOS et Windows__
__-Une autre option pouvant être utilisée est MongoDB Compass__

![13.png](http://c1.maroun.xyz/github_screenshots/13.png)


**Exemple Compass sur Mac OSX**
![18.png](http://c1.maroun.xyz/github_screenshots/18.png)


## Parlons de MySQL

**Une note à propos de SQL**

Le code SQL, quant à lui, représente un langage de requête structuré.

SQL est le langage normalisé utilisé pour accéder à la base de données.

SQL contient trois parties:

- Le langage de définition de données comprend des instructions qui vous aident à définir la base de données et ses objets, par exemple des tables, des vues, des déclencheurs, des procédures stockées, etc.
- Le langage de manipulation de données contient des instructions permettant de mettre à jour et d'interroger des données.
- Le langage de contrôle des données vous permet d'accorder les autorisations à un utilisateur pour accéder à des données spécifiques de la base de données.

**Qu'en est-il de MySQL?**

MySQL est un système de gestion de base de données relationnelle (SGBDR) à source ouverte et complète, initialement créé par MySQL AB et actuellement détenu par Oracle Corporation. Il stocke les données dans des tables regroupées dans une base de données, utilise le langage SQL (Structured Query Language) pour accéder aux données et des commandes telles que «SELECT», «UPDATE», «INSERT» et «DELETE» pour le gérer. Les informations associées peuvent être stockées dans différentes tables, mais l'utilisation de l'opération JOIN vous permet de les corréler, d'effectuer des requêtes sur différentes tables et de minimiser les risques de duplication de données.

MySQL est compatible avec presque tous les systèmes d'exploitation, à savoir Windows, Linux, Unix, Apple, FreeBSD et beaucoup d'autres. Il supporte divers moteurs de stockage, tels que InnoDB (par défaut), Federated, MyISAM, Memory, CSV, Archive, Blackhole et Merge.


## MongoDB vs MySQL

**Une note sur les bases de données relationnelles / non relationnelles:**

Les bases de données relationnelles ont tenu le leadership pendant des décennies et à ce moment-là, le choix était évident: MySQL, Oracle ou MS SQL, pour n'en nommer que quelques-uns. Elles ont servi de base à des tonnes d’applications d’entreprise, alors que les applications modernes exigent davantage de diversité et d’évolutivité. Les bases de données non relationnelles, telles que MongoDB, semblent répondre aux exigences existantes et remplacer l'environnement relationnel actuel.

**Comparaison côte à côte:**

![14.png](http://c1.maroun.xyz/github_screenshots/14.png)


**MySQL vs MongoDB: avantages et inconvénients**

Il est difficile de comparer les performances de MongoDB à celles de MySQL, car les deux systèmes de gestion sont extrêmement utiles et que les différences fondamentales sous-tendent leurs opérations de base et leur approche initiale. Cependant, MongoDB vs MySQL est un argument brûlant qui dure depuis un moment maintenant: une base de données relationnelle mature contre un jeune système non relationnel. Les deux sont open-source et facilement disponibles, ainsi que les deux systèmes offrent des versions commerciales avec des tonnes de fonctionnalités supplémentaires.

![15.png](http://c1.maroun.xyz/github_screenshots/15.png)


**Quelle base de données choisir?**

Pour répondre à la question principale: "Quand utiliser MongoDB au lieu de MySQL?", Vous devez tenir compte des exigences de votre projet et de vos objectifs. MySQL est reconnu pour ses hautes performances, sa flexibilité, sa protection fiable des données, sa haute disponibilité et sa facilité de gestion. Une indexation correcte des données peut résoudre le problème en termes de performances, faciliter les interactions et assurer la robustesse. Mais si vos données sont complexes et non structurées, ou si vous ne pouvez pas prédéfinir votre schéma, vous feriez mieux d’opter pour MongoDB. De plus, si vous devez gérer un grand volume de données et les stocker sous forme de documents, MongoDB vous aidera à relever les défis.


## Exemple de codage MongoDB / MySQL

**Configuration sur MySQL et importation de la base de test**

Afin de coder notre propre environnement de test (pour mongoDB et mysql), nous avons besoin d’un exemple de base de données. Nous allons utiliser celui par défaut de MySQL:

https://github.com/datacharmer/test_db

```
 mysql -u root -p < /var/www/c1/dbs/test_db-master/employees.sql
```

![16.png](http://c1.maroun.xyz/github_screenshots/16.png)


**Vérifier l'importation de la base de données MySQL**

![17.png](http://c1.maroun.xyz/github_screenshots/17.png)


**Configuration sur MongoDB et importation de la base de test**

Pour MongoDB, il est en fait plus facile d'importer la base de test, vous pouvez en trouver un par le biais:

```
wget http://media.mongodb.org/zips.json
mongoimport -v --file=zips.json
```

**Vérifier l'importation de la base de données MongoDB**

![18.png](http://c1.maroun.xyz/github_screenshots/18.png)


**Commençons à coder! - partie PHP**

```
<?php
$servername = "localhost";
$username = "root";
$password = "root";
$dbname = "employees";

// Create connection
$conn = new mysqli($servername, $username, $password, $dbname);
// Check connection
if ($conn->connect_error) {
	die("Connection failed: " . $conn->connect_error);
}

$table_name='employees';

$sql = "SELECT emp_no, first_name, last_name FROM $table_name";
$result = $conn->query($sql);

if ($result->num_rows > 0) {
	while($row = $result->fetch_assoc()) {
		echo "id: " . $row["emp_no"]. " - Name: " . $row["first_name"]. " " . $row["last_name"]. "<br>";
	}
} else {
	echo "0 results";
}
$conn->close();
?>
```

**Commençons à coder! - partie MongoDB**

```
<?php
$m = new Mongo();
$db = $m->selectDB('test');

// MongoCollection, pasing $db and collection name
$collection = new MongoCollection($db, 'zips');

// Your query
$cursor = $collection->find();
var_dump($cursor);
?>
```


---
title: Bases de dades
---

# Bases de dades

Moltes vegades el codi PHP fan servir una base de dades per guardar la informació. Vostè té diverses opcions per connectar i interactuar amb la base de dades. L'opció recomanada _fins PHP 5.1.0_  es utilitzar controladors nadius, com ara [MySQL][mysql], [MySQLi][mysqli], [PgSQL][pgsql], etc.

Els controladors nadius són una molt bona opció si vostè vol utilitzar només una base de dades en l'aplicació, però si per exemple, està utilitzant MySQL i una mica de MSSQL, o necesitas utilitza la connexió a una base de dades Oracle, llavors vostè no serà capaç d'utilitzar els mateixos controladors. Hauràs dependre de nous APIs per a cada base de dades; i això pot ser una ximpleria.

Com una nota addicional pels controladors nadius, l'extensió MySQL per PHP ja no està en actiu desenvolupament i l'estatus oficial a partir de PHP 5.4 és "la depreciació a llarg termini". Això vol dir que s'eliminarà en les properes versions, així que per PHP 5.6 (o el que vingui a continuació 5.5), ja podia ser que s'hagi eliminat completament. 

Si utilitzeu `mysql_connect()` i `mysql_query()` en les seves aplicacions tindreu que reescriure algunes parts del vostre codi, pròximament. De manera que la millor opció és reemplaçar l'ús de MySQL amb MySQLi o PDO en les seves aplicacions de desenvolupament, per no fer-ho mes endavant. _Si vostè està començant des de zero llavors absolutament NO utilitzar l'extensió MySQL: utilitzeu la [extensió MySQLi][MySQLi], o utilitzar PDO._

* [PHP: L'elecció d'un API per a MySQL](http://php.net/manual/en/mysqlinfo.api.choosing.php)

## PDO

PDO és una biblioteca d'abstracció connexió de base de dades &mdash; incorporat en PHP des 5.1 &mdash; que proporciona una interfície comuna per parlar amb moltes bases de dades diferents. PDO no tradueix les consultes SQL ni tampoc emular les característiques que li falten, és purament per a la connexió a múltiples tipus de base de dades amb la mateixa API.

Una característica molt important de `PDO` permet injectar de forma segura la participació de usuaris externs (per exemple pels: IDs) en les consultes SQL sense haver de preocupar-te sobre els atacs d'injecció de bases de dades SQL. Això és possible mitjançant declaracions PDO i paràmetres enllaçats.

Suposem que un script PHP rep un identificador numèric com un paràmetre de consulta. Aquest ID s'ha d'utilitzar per anar a buscar un registre d'usuari a partir d'una base de dades. Aquesta és la manera `incorrecta` de fer això:

{% highlight php %}
<?php
$pdo = new PDO('sqlite:usuaris.db');
$pdo->query("SELECT nom FROM usuaris WHERE id = " . $_GET['id']); // <-- NO! (Aquesta és la manera incorrecta)
?>
{% endhighlight %}

Aquest és el codi terrible horripile! Se està inserint un paràmetre de consulta en brut en una consulta SQL. Imagineu si un hacker passa en al paràmetre `id` inventat, cridant a una URL com `http://domini.com/?id=1%3BDELETE+FROM+users`. Això farà que la variable `$_GET['id']` passi el valor `1;DELETE FROM usuaris` i la conseqüència es que se elimini tots els usuaris de la base de dades!

En el seu lloc, vostè ha de desinfectar l'entrada ID amb els paràmetres de PDO:

{% highlight php %}
<?php
$pdo = new PDO('sqlite:usuaris.db');
$stmt = $pdo->prepare('SELECT nom FROM usuaris WHERE id = :id');
$stmt->bindParam(':id', $_GET['id'], PDO::PARAM_INT); // <-- Si! (Desinfectat automàticament per PDO)
$stmt->execute();
?>
{% endhighlight %}

Aquest és el codi `correcte`. S'utilitza un paràmetre dependent en un comunicat PDO. Això escapa a l'entrada del ID del usuari extern abans de la seva introducció a la base de dades, així prevenim els atacs d'injecció SQL.

* [Aprèn sobre PDO][1]

També ha de ser conscient de que les connexions de base de dades utilitzen recursos i així que sempre que es pot es molt recomanable tancar les connexions. Fen servir PDO pots implícitament tancar la connexió mitjançant la destrucció de l'objecte, garantint totes les referències restants perquè s'eliminen, és a dir que se'ls estableix  com a valor NULL. Pero si falla, PHP haura de esperar fins que l'script finalitzi, a menys que vostè estigui utilitzant connexions persistents.

* [Aprèn sobre connexions PDO][5]

## Capes d'abstracció

Molts *frameworks* proporcionen la seva pròpia capa d'abstracció que pot o no pot utilitzar com a capa superior PDO. Aquests solen emular les característiques per al sistema de base de dades d'una que altra falta d'un altre, embolicant les seves consultes en els mètodes PHP, donant-li abstracció de base de dades real. Això per descomptat, afegir una petita sobrecàrrega, però si vostè està creant una aplicació portable que necessita per treballar amb MySQL, PostgreSQL i SQLite llavors una petita sobrecàrrega valdrà la pena per neteja del codi.

Algunes capes d'abstracció s'han construït utilitzant el PSR-0 estàndard de espai de noms pel que pot instal·lar en qualsevol aplicació que vulguis:

* [Aura SQL][6]
* [Doctrine2 DBAL][2]
* [ZF2 Db][4]
* [ZF1 Db][3]

[1]: http://www.php.net/manual/en/book.pdo.php
[2]: http://www.doctrine-project.org/projects/dbal.html
[3]: http://framework.zend.com/manual/en/zend.db.html
[4]: http://packages.zendframework.com/docs/latest/manual/en/index.html#zend-db
[5]: http://php.net/manual/en/pdo.connections.php
[6]: https://github.com/auraphp/Aura.Sql

[mysql]: http://php.net/mysql
[mysqli]: http://php.net/mysqli
[pgsql]: http://php.net/pgsql

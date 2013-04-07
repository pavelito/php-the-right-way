---
title: Interfície de Línia de Comandament
isChild: true
---

## Interfície de Línia de Comandament

PHP va ser creat principalment per desenvolupar aplicacions web, però també és molt útil per implementar programes que corren en la interfície de línia d'ordres (CLI). Els programes de línia d'ordres en PHP poden ajudar a automatitzar tasques comunes com proves, desplegaments i l'administració d'aplicacions.

Els programes CLI en PHP són molt potents perquè el codi de l'aplicació es pot utilitzar directament sense haver de crear o assegurar un GUI web per al seu ús. Per això, assegureu-vos de no col·locar els seus programes CLI en el seu directori arrel públic!

Proveu córrer PHP des de la consola de comandes:

{% highlight bash %}
> php -i
{% endhighlight %}

L'opció `-i` imprimirà la configuració de PHP, com succeeix amb la funció [`phpinfo`][phpinfo].
L'opció `-a` habilita una consola interactiva molt similar a IRB de Ruby o la consola interactiva de Python. Hi ha diverses [opcions de línia de comandes] [cli-options] que resulten molt útils.
Anem a escriure un programa simple que imprimeixi "Hola, $nom" a la línia de comandes. Per començar, crearem un arxiu anomenat `hola.php` com es mostra a continuació:

{% highlight php %}
<?php
if($argc != 2) {
    echo "Us: php hola.php [nom].\n";
    exit(1);
}
$nom = $argv[1];
echo "Hola, $nom\n";
{% endhighlight %}

PHP fa disponibles dues variables especials basats en els arguments que rep el programa al ser executat. El variable de tipus _enter_ [`$argc`][argc] conté el *count* o nombre d'arguments i la variable de tipus _array_ [`$argv`][argv] conté el *value* o valor de cadascun dels arguments que es van passar durant l'execució. El primer argument sempre és el nom del fitxer del programa PHP, que en aquest cas és `hola.php`.

L'expressió `exit()` es pot utilitzar amb un nombre que no és zero per deixar saber a la consola que la comanda ha fallat. [Aquí][exit-codes] pot trobar els codis de sortida més comunament usats.

Per executar el programa des de la línia de comandes:

{% highlight bash %}
> php hola.php
Uso: php hola.php [nombre]
> php hola.php món
Hola, món
{% endhighlight %}

* [Aprengui sobre l'execució de PHP des de la línia d'ordres][php-cli]
* [Aprengui com configurar el Windows per executar PHP des de la línia d'ordres][php-cli-windows]

[phpinfo]: http://php.net/manual/es/function.phpinfo.php
[cli-options]: http://www.php.net/manual/es/features.commandline.options.php
[argc]: http://php.net/manual/es/reserved.variables.argc.php
[argv]: http://php.net/manual/es/reserved.variables.argv.php
[php-cli]: http://php.net/manual/es/features.commandline.php
[php-cli-windows]: http://www.php.net/manual/es/install.windows.commandline.php
[exit-codes]: http://www.gsp.com/cgi-bin/man.cgi?section=3&topic=sysexits
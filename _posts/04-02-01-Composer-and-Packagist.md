---
title: Composer i Packagist
isChild: true
---

## Composer i Packagist

Composer és un **excel·lent** gestor de dependències per a PHP. Només ha d'afegir les dependències del seu projecte a un arxiu anomenat `composer.json`, executar algunes ordres i Composer descarregarà automàticament les dependències per al seu projecte i configurarà el carregador automàtic en qüestió de segons.

Ja hi ha moltes llibreries PHP compatibles amb Composer i estan llestes perquè les utilitzeu en projecte. Hi ha una llista d'aquests "paquets" al lloc [Packagist][1], que és el dipòsit oficial de llibreries compatibles amb Composer.

### Com configurar Composer

Es pot instal·lar Composer local (en el directori de treball actual, encara que això ja no és recomanable) o globalment (per exemple, a /user/local/bin). Suposem que vostè vol configurar Composer localment, des del directori arrel del seu projecte:

    curl -s http://getcomposer.org/installer | php

Això us descarregarà l'arxiu binari `composer.phar`. Es pot executar aquest comandament amb `php` per manejar les dependències del seu projecte. *Si us plau, tingui en compte*: Si executeu el codi directament a l'intèrpret de PHP al mateix temps que el descarrega, aneu en compte de llegir el codi del programa amb anterioritat i confirmar que és segur.

### Com configurar Composer (manualment)

Configura Composer manualment requereix tècniques avançades. Tanmateix, hi ha diverses raons per les quals un desenvolupador com vostè prefereixi configurar d'aquesta manera en lloc d'utilitzar la rutina de configuració interactiva. La configuració interactiva verifica el seu sistema de PHP per assegurar que:

- Està utilitzant una versió compatible de PHP
- Els arxius `. Phar` poden ser executats correctament
- Té suficients permisos en els directoris
- Algunes extensions que poden causar problemes no han estat carregades
- L'arxiu `php.ini` ha els paràmetres necessaris

Ja que la configuració manual no realitza cap d'aquestes verificacions, necessita prendre en consideració si tal funcionament és el que vostè desitja. De tota manera, vostè pot obtenir i configurar Composer manualment de la següent manera:

    curl -s http://getcomposer.org/composer.phar -o $HOME/local/bin/composer
    chmod +x $HOME/local/bin/composer

La ruta `$HOME/local/bin` (o un directori que vostè esculli) necessita estar en el variable d'entorn `$PATH`. D'aquesta manera, el comandament `composer` trobareu a qualsevol directori del sistema.

Quan es trobi amb instruccions que li suggereixin executar Composer amb `php composer.phar install`, això es pot substituir amb:

    composer install

### Com Definir i Configura dependències

Primer, es crea un arxiu `composer.json` en el mateix directori on es troba `composer.phar`. Tot seguit, trobem un exemple que defineix el paquet [Twig][2] com una dependència del projecte:

	{
	    "require": {
	        "twig/twig": "1.8.*"
	    }
	}

El següent pas és executar Composer des del directori arrel del seu projecte:

    php composer.phar install

Això descarregarà i configurarà la dependència dins d'un directori anomenat `vendors/`. Un cop configurat, afegiu aquesta línia de codi a l'arxiu principal de la seva aplicació:

{% highlight php %}
<?php
require 'vendor/autoload.php';
{% endhighlight %}

Aquesta instrucció li diu al seu programa que utilitzeu el carregador automàtic de Composer per carregar qualsevol dependència que hagi configurat. Ara les seves dependències produiran dinàmicament segons el seu programa les requereixi.

* [Aprengui més sobre Composer][3]

[1]: http://packagist.org/
[2]: http://twig.sensiolabs.org
[3]: http://getcomposer.org/doc/00-intro.md

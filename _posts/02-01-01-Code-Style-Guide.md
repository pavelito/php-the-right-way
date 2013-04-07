---
title: Guía de Estilo de Código
---

# Guia d'Estil de Codi

La comunitat darrere de PHP és enorme i diversa, composta d'innombrables llibreries, estructures base de desenvolupament (*frameworks*) i components. És comú que desenvolupadors en PHP escullin d'entre aquests i els combinin en un sol projecte. Per això és important que el codi PHP s'adhereixi (el més a prop possible) a un estil de codi comú perquè es faciliti el treball dels desenvolupadors en combinar una varietat de llibreries per als seus projectes.

El [Framework Interop Group][fig] (abans conegut com el 'PHP Standards Group') ha proposat i aprovat una sèrie de recomanacions d'estil, conegudes com [PSR-0][psr0], [PSR-1][psr1] i [PSR-2][psr2]. No deixeu que els títols rars us confonguin, aquestes recomanacions són simplement un conjunt de normes que alguns projectes com Drupal, Zend, CakePHP, phpBB, AWS SDK, FuelPHP, Lithium i altres, han començat a adoptar. Vostè pot utilitzar aquestes normes en els seus propis projectes o continuar amb el vostre propi estil.

Seria ideal que escrivís codi PHP que s'adhereix a un o més d'aquests estàndards perquè altres desenvolupadors puguin llegir i treballar amb el seu codi fàcilment. Els estàndards se afegeixen a l'estàndard previ, així que utilitzar PSR-1 requerix el us de PSR-0, però no requereix PSR-2.

* [Llegiu sobre PSR-0][psr0]
* [Llegiu sobre PSR-1][psr1]
* [Llegiu sobre PSR-2][psr2]

Podeu utilitzar la configuració de [phpcs-psr][phpcs-psr] per l'eina [phpcs-psr][phpcs-psr] i verificar que el seu codi s'adhereixi a les normes i recomanacions estipulades en aquests estàndards. També podeu fer servir el [PHP Coding Standards Fixer][phpcsfixer] de Fabien Potencier per modificar el sintaxi del seu codi i així automàticament es conformi a aquests estàndards, estalviant el temps i esforç que requeriria arreglar el problema a mà.

[fig]: http://www.php-fig.org/
[psr0]: https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-0.md
[psr1]: https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-1-basic-coding-standard.md
[psr2]: https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-2-coding-style-guide.md
[phpcs]: http://pear.php.net/package/PHP_CodeSniffer/
[phpcs-psr]: https://github.com/klaussilveira/phpcs-psr
[phpcsfixer]: http://cs.sensiolabs.org/

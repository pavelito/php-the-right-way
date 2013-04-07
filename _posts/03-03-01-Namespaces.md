---
title: Espais de Noms
isChild: true
---

## Espais de Noms

Com hem dit anteriorment, la comunitat de PHP té molts desenvolupadors creant una gran quantitat de codi font. Això vol dir que hi ha la possibilitat que dues llibreries diferents utilitzin el mateix nom per a una classe en el seu codi. Quan les dues llibreries s'usen dins el mateix espai de noms això s'anomena com una col·lisió i pot causar problemes.

Els _Espais de Noms_ resolen aquest problema. Com es descriu en el manual de referència de PHP, els espais de noms són similars als directoris que separen els arxius en el sistema operatiu. Dos arxius amb el mateix nom poden coexistir en directoris separats. Igualment, dues classes de PHP amb el mateix nom poden coexistir en espais de noms separats, és tan simple com això.

És important que separi el seu codi amb un espai de noms perquè pugui ser usat per altres desenvolupadors sense la preocupació que causi problemes amb altres llibreries.

Un dels mètodes recomanats per a l'ús d'espais de noms s'indica al [PSR-0][psr0], el qual es proposa proveir una convenció estàndard per als arxius, classes i els espais de noms, la qual cosa facilita l'intercanvi i ús del codi en diferents projectes.


* [Llegir sobre els Espais de Noms][namespaces]
* [Llegir sobre el PSR-0][psr0]

[namespaces]: http://php.net/manual/es/language.namespaces.php
[psr0]: https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-0.md

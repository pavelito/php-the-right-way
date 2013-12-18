---
title: Paradigmes de Programació
isChild: true
---

## Paradigmes de Programació

PHP és un llenguatge flexible i dinàmic que permet utilitzar una varietat de tècniques de programació. El llenguatge ha evolucionat dramàticament a través dels anys. Es va afegir un model d'objectes (object-oriented) sòlid en la versió 5.0 (2004), funcions anònimes i espais de noms (namespaces) en PHP 5.3 i trets (traits) en PHP 5.4 (2012).

### Programació Orientada a Objectes

PHP té un conjunt molt complet d'aspectes que faciliten la programació orientada a objectes (OOP) que inclou l'habilitat de crear classes, classes abstractes, interfícies, herència, constructors, clonació d'objectes, excepcions i molt més.

* [Llegir més sobre PHP orientat a objectes][oop]
* [Llegir més sobre Trets][traits]

### Programació Funcional

PHP té la capacitat de declarar funcions de primera classe, en altres paraules, una funció pot ser assignada a un variable. Les funcions definides per l'usuari, així com les funcions internes (incloses), té l'habilitat de ser referenciades per un variable i invocades dinàmicament. Les funcions poden ser passades com a arguments a altres funcions (un aspecte anomenat funcions d'ordre superior) i funcions poden retornar altres funcions.

La recursivitat és un aspecte que li permet a una funció a cridar-se a si mateixa. El llenguatge PHP habilita aquest tipus d'algorismes, però, la majoria del codi PHP s'enfoca en iteració.

Les funcions anònimes (amb suport per clausures) estan presents en PHP des de la versió 5.3 (2009).

En PHP 5.4 es va afegir l'habilitat per vincular clausures a l'àmbit d'un objecte i també es va millorar el suport de funcions de tipus exigibles (*callables*) perquè puguin intercanviar amb funcions anònimes en gairebé tots els casos.

* Continueu llegint sobre la [programació funcional en PHP](/pages/Functional-Programming.html)
* [Llegir sobre les funcions anònimes][anonymous-functions]
* [Llegir sobre la classe clausura][closure-class]
* [Més detalls definits al RFC de clausures][closures-rfc]
* [Llegir sobre funcions tipus exigibles][callables]
* [Llegir sobre com invocar funcions amb `call_user_func_array`][call-user-func-array]

### Programació Meta

PHP suporta diverses formes de programació meta mitjançant mecanismes com l'API de Reflexió i els Mètodes Màgics. Hi ha molts Mètodes Màgics disponibles com  `__get()`, `__set()`, `__clone()`, `__toString()`, `__invoke()` i més, que permeten als desenvolupadors a connectar amb el funcionament de la classe. Sovint desenvolupadors en Ruby diuen que a PHP li falta la funció de `method_missing`, però els aspectes d'aquesta funció estan disponibles en `__call()` i `__callStatic()`.

* [Llegir sobre els Mètodes Màgics][magic-methods]
* [Llegir sobre Reflexion][reflection]

[namespaces]: http://php.net/manual/es/language.namespaces.php
[overloading]: http://uk.php.net/manual/es/language.oop5.overloading.php
[oop]: http://www.php.net/manual/es/language.oop5.php
[anonymous-functions]: http://www.php.net/manual/es/functions.anonymous.php
[closure-class]: http://php.net/manual/es/class.closure.php
[callables]: http://php.net/manual/es/language.types.callable.php
[magic-methods]: http://php.net/manual/es/language.oop5.magic.php
[reflection]: http://www.php.net/manual/es/intro.reflection.php
[traits]: http://www.php.net/manual/es/language.oop5.traits.php
[call-user-func-array]: http://php.net/manual/es/function.call-user-func-array.php
[closures-rfc]: https://wiki.php.net/rfc/closures

---
title: Gestió de Dependències
---

# Gestió de Dependències

Hi ha un gran nombre de llibreries, estructures base de desenvolupament (*frameworks*) i components de PHP d'on escollir i el més probable és que el seu projecte utilitzi diversos. A aquests se'ls crida dependències de projecte. Fins molt recentment, PHP no tenia una manera fàcil de gestionar aquests dependències. Encara que siguis es feia càrrec d'aquests manualment, encara hauria de mantenir-se al tant dels carregadors automàtics (autoloaders). Ara ja no és així.

Actualment hi ha dos sistemes principals de gestió de paquets per a PHP: Composer i PEAR. Quin és l'adequat per a vostè? La resposta és, tots dos.

* Utilitzeu **Composer** quan manegi les dependències d'un sol projecte.

* Utilitzeu **PEAR** quan manegi les dependències de tot el sistema de PHP en la seva plataforma.

Generalment, els paquets de Composer només estaran disponibles en els projectes que especifiqueu explícitament, mentre que un paquet de PEAR estaria disponible a tots els projectes sota el sistema PHP. Potser PEAR sembli la proposta més accessible a primera vista, però, també hi ha avantatges per treballar amb les dependències amb Composer sobre la base del projecte en què s'està treballant.

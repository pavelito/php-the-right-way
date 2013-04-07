---
title: Configuració en Mac
isChild: true
---

## Configuració en Mac

El sistema OSX ve configurat prèviament amb un PHP que normalment no esta actualitzada a la versió actual. El sistema de "Lion" està configurat amb PHP 5.3.6 i el sistema de "Mountain Lion" posa a disposició la versió 5.3.10.

Para actualitzar la versió de PHP en el sistema OSX es pot instal·lar per diferents medis de [gestors de paquets][mac-package-managers], no obstant, nosaltres recomanem el paquet [php-osx by Liip][php-osx-downloads].

L'altra opció disponible és que [vostè compili][mac-compile] el paquet d'instal·lació. En aquest cas, a de ser segur de tenenir la aplicació per desenvolupar el _Xcode_ o, com a substitut les eines ["Command Line Tools for Xcode"][apple-developer] que es pot descarregar directament des del _centre de desenvolupadors de Mac_ de Apple.

També hi ha un paquet tipus "tot en un", amb un simple control gràfic de configuració, anomenada [MAMP][mamp-downloads]. Això inclou una configuració de PHP juntament amb el servidor web Apache i gestor de base de dades de MySQL.

[mac-package-managers]: http://www.php.net/manual/en/install.macosx.packages.php
[mac-compile]: http://www.php.net/manual/en/install.macosx.compile.php
[xcode-gcc-substitution]: https://github.com/kennethreitz/osx-gcc-installer
[apple-developer]: https://developer.apple.com/downloads
[mamp-downloads]: http://www.mamp.info/en/downloads/index.html
[php-osx-downloads]: http://php-osx.liip.ch/

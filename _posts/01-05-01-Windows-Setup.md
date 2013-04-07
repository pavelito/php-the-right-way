---
title: Configuració de Windows
isChild: true
---

## Configuració de Windows

Hi ha moltes maneres de configurar PHP en el sistema operatiu Windows. Vostè pot [descarregar els binaris](php-downloads) i fins fa poc, podies utilitzar un instal·lador format ".msi". Aquest paquet d'instal·lació ja no està actualitza i és l'última versió va ser PHP 5.3.0.

Per aprendre PHP o el desenbulupament local, es pot ulilitzar el servidor web incrustat que ve amb la versió de PHP 5.4, així no caldrà que es preocupi de configurar un servidor per separat. Ara bé, si li agradaria tenir una solució tipus "tot en un", que li ofereix un servidor de web complet junt amb el gestor de base de dades MySQL, aleshores eines com el [Web Platform Installer][wpi], [XAMPP][xampp] i [WAMP][wamp] l'ajudaran a configurar un entorn de desenvolupament web en Windows més fàcilment i en menys temps. Tingui en consideració que aquestes eines son una mica diferents a les que faràs servir en el seu sistema de producció, aixi que tingui precaució de les diferencies en el entorn de la seva aplicació si es que desenvolupa en Windows però la desplegara en Linux.

Si necessita corre un sistema de producció en Windows aleshores el servidor IIS 7, li oferira un entorn mes estable i amb el millor rendiment. Una eina com [phpmanager][phpmanager] (un complement GUI per IIS 7) li simplificara la gestió i configuració de PHP en aquest servidor. IIS 7 ve configurat amb FastCGI llest per el seu us, nomes necessita apuntar a PHP com controlador. Per més informació i recursos adicionals referiu-vos a la [àrea dedicada en iis.net][php-iis] per PHP.

En general, el que corre la seva aplicació en diferents entorns per desenvolupar i produir pot portar a que se manifestin errors estranys al fer servir la seva aplicació. Si esta desenvolupant en Windows i desplegant en Linux (o qualsevol altre sistema que no sigui Windows) considera el us de una maquina virtual. Potser sona una mica complicat, però amb el us de [Vagrant][vagrant] pots configurar contenidors simples les quals es poden disposar fàcilment amb [Puppet][puppet] o [Chef][chef] i compartir-los amb els seus amics per assegurar que tot el seu equip de desenvolupament estigui treballant amb el mateix sistema.

[php-downloads]: http://windows.php.net
[phpmanager]: http://phpmanager.codeplex.com/
[wpi]: http://www.microsoft.com/web/downloads/platform.aspx
[xampp]: http://www.apachefriends.org/en/xampp.html
[wamp]: http://www.wampserver.com/
[php-iis]: http://php.iis.net/
[vagrant]: http://vagrantup.com/
[puppet]: http://www.puppetlabs.com/
[chef]: http://www.opscode.com/
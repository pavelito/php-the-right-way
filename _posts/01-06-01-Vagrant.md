---
title: Vagrant
isChild: true
---

## Vagrant

Corrent la vostre aplicació en diferents entorns en desenvolupament i producció pot conduir a errors estranys que fan esclatar per amunt del vostre nivell. També és difícil de mantenir entorns de desenvolupament diferents al dia amb la mateixa versió per a totes les biblioteques que utilitzen quan es treballa amb un equip de desenvolupadors.

Si estas desenvolupant en Windows i la implementació es fa en Linux (o qualsevol altre sistema que no sigui Windows) o estan desenvolupant en un equip, ha de considerar l'ús d'una màquina virtual. Això sona complicat, però amb [Vagrant][vagrant] vostè pot configurar una màquina virtual simple amb només uns pocs passos. Aquesta caixa base es pot configurar manualment, o bé pot utilitzar programari com [Puppet][puppet] o [Chef][chef] que farà aquesta tasque per tu. La caixa base és una gran manera d'assegurar-se que les caixes múltiples es configuren en forma idèntica i elimina la necessitat per tu, la de “crear” les llistes d'ordres. També pot "destruir" la seva caixa base i tornar-la a crear amb molt pocs passos manuals, es fàcil crear un "fresc" de la instal·lació.

Vagrant crea carpetes per compartir el vostre codi entre el vostre amfitrió i la vostra màquina virtual, significa pot crear i editar els vostres arxius en la vostra màquina amfitriona i llavors executar-los dins la vostra màquina virtual.

[vagrant]: http://vagrantup.com/
[puppet]: http://www.puppetlabs.com/
[chef]: http://www.opscode.com/

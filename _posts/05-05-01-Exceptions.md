---
title: Excepcions
isChild: true
---

## Excepcions

Les **Excepcions** són un aspecte normal dels llenguatges de programació més populars, peró sovint són pasades per alt pels programadores de PHP. Altres llenguatges com Ruby utilitzen les **Excepcions** en gran quantitat, tant que cada vagada que succeeix un error com una petició HTTP que ha fallat o una línia de consulta a una base de dades que no funciona, o potser hi havia una imatge que no existeix, Ruby (o qualsavol gama en ejecució) llança una excepció a la pantalla deixant a coneix-re que hi va haver-hi un error.

PHP es poc exigent en aquestes instancies. Per exemple, una trucada a la funció `file_get_contents()` usualment sol retornar un `FALSE` i una advertència. Molts de les estructures base (frameworks) més antigues de PHP com CodeIgniter simplement retorna un valor `FALSE`, i registren un missatge en els seus registres i potser el permetin utilitzar un mètode com `$this->upload->get_error()` per veure que funciona malament. El problema amb aquests es que un mateix te que anar a buscar el error i assegurar-se en la documentació de quin dels mètodes per verificar errors a de utilitzar, en comptes de fer que el error sigui més obi.

Un altre problema comú es quan les classes automaticament llancen un error a la pantalla i paren el flux del programa. Quan aixó passa el desenvolupador no te la oportunitat de manejar el error dinàmicamenet. En aquesta instancia es tenene que utilitzar les excepcions per que el desenvolupador estigui conscient de que hi ha un error i pot escollir com manejar la situació. Per exemple: correu electrònic

{% highlight php %}
<?php
$correuElectronic = new Fuel\Email;
$correuElectronic->subject('El Meu Assumpte');
$correuElectronic->body('Como estas?');
$correuElectronic->to('persona@exemple.com', 'Algun persona');

try
{
    $correuElectronic->send();
}
catch(Fuel\Email\ValidationFailedException $e)
{
    // Hi va haver un error en la validació
}
catch(Fuel\Email\SendingFailedException $e)
{
    // El gestor no va poder enviar el correu
}
{% endhighlight %}

### Excepcions de la SPL

Les excepcions, per defecte, no tenen cap significat i el mètode més comú de asignárselos és en donar-los un nom:

{% highlight php %}
<?php
class ValidationException extends Exception {}
{% endhighlight %}

Això li permet afegir múltiples blocs `catch` i manejar diferents excepcions de diferent manera. Això pot conduir a la creació d'una gran quantitat d'excepcions particulars només a la seva aplicació, moltes de les quals poguessin eliminar en usar les excepcions que proveeix la [extensió de la SPL][splext].

Si, per exemple, utilitza el mètode màgic `__call()` i aquest sol·licita un mètode invàlid, llavors en comptes de llançar una excepció estàndard de significat dubtós o crear una excepció particular, només caldrà fer aixó:

{% highlight php %}
<?php
throw new BadFunctionCallException;
{% endhighlight %}


* [Llegir sobre les Excepcions][exceptions]
* [Llegir sobre les Excepcions de la SPL][splexe]
* [Com niar excepcions en PHP][nesting-exceptions-in-php]
* [Les millors pràctiques per a les excepcions en PHP 5.3][exception-best-practices53]

[exceptions]: http://php.net/manual/es/language.exceptions.php
[splexe]: http://php.net/manual/es/spl.exceptions.php
[splext]: /#biblioteca_estándar_de_php
[exception-best-practices53]: http://ralphschindler.com/2010/09/15/exception-best-practices-in-php-5-3
[nesting-exceptions-in-php]: http://www.brandonsavage.net/exceptional-php-nesting-exceptions-in-php/

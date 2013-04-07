---
title: Data i Hora
isChild: true
---

## Data i Hora

PHP disposa de una classe anomenada **DateTime** que t'he ajuda en la lectura, escriptura, comparacions i calculació de les dades i les hores. Existeixen moltes funcions en PHP relacionades amb el manipulació de dates i hores, però la classe **DateTime** prove amb una millor interfície orientada a objectes per les situacions més comunes. També tenen la capacitat de utilitzar els fusos horaris (però aquest funció la considerem fora de la nostra petita introducció).

Per començar a traballar amb DateTime primer tenim que convertir les cadenes de textos les que contenen la data i l'hora, a un objecte amb el mètode de fabricació `createFromFormat()` o també ho podem crear un objecte amb `new \DateTime` que contindrà la data i l'hora actual. Después, pot utilitzar el mètode `format()` per convertir el objecte DateTime a altre cop a una cadena de text i imprimir-la:

{% highlight php %}
<?php
$data = '22. 11. 1968';
$inici = \DateTime::createFromFormat('d. m. Y', $data);

echo "Data de Inici: " . $inici->format('m/d/Y') . "\n";
{% endhighlight %}

Es pot utilitzar la classe DateInterval per realitzar calculacions amb DateTime. La classe DateTime te mètodes amb `add()` i `sub()` que requereixen que es pasi un DateInterval com argument. Mai escriguis codi que compte amb el mateix numero de segons en tots els dies, ja que els ajusta del fusos horaris i el horari de estiu (daylight savings time) invalidaría aquesta suposició. En comptes d'això, utilitza els intervals de dates per fer les seves calculacions. Per calcular la diferencia entre dades utilitza el mètode `diff()`. Aquest li retornarà un `return new DateInterval`, el qual pot ser fàcilment imprès en a la pantalla.

{% highlight php %}
<?php
// Crea un copia de %inici i afegeix un mes i 6 dies
$final = clone $inici;
$final->add(new \DateInterval('P1M6D'));

$diferencia = $final->diff($inici);
echo "Diferencia: " . $diff->format('%m mes, %d dies (total: %a dies)') . "\n";
// Diferencia: 1 mes, 6 dies (total: 37 dies)
{% endhighlight %}

Es posible comparar fàcilmente els objectes DateTime:

{% highlight php %}
<?php
if($inici < $final) {
    echo "¡El inici succeeix abans que el final!\n";
}
{% endhighlight %}
    
Aquest ultim exemple demostre com s'utilitza la classe DatePeriod per iterar sobre incidències. El objecte pren 2 objectes DateTime, un per el inici i l'altre per el final, i el interval que defineix el numero de incidències periòdiques que es retornen.

{% highlight php %}
<?php
// Imprimir tots els dijous entre $inici i $final
$intervalDePeriode = \DateInterval::createFromDateString('first thursday');
$intervalDePeriode = new \DatePeriod($inici, $intervalDePeriode, $final, \DatePeriod::EXCLUDE_START_DATE);
foreach($intervalDePeriode as $data)
{
    // Imprimir cada data en el període
    echo $data->format('m/d/Y') . " ";
}
{% endhighlight %}

* [Llegeix sobre la classe DateTime][datetime]
* [Com formatatjar la data][dateformat] (Opcions dels formats acceptats per una data)

[datetime]: http://php.net/manual/es/book.datetime.php
[dateformat]: http://php.net/manual/es/function.date.php

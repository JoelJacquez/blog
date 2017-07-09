---
layout: post
title: "Funciones prácticas con fechas"
date: 2017-07-07 17:26:45 -0500
comments: true
categories: JavaScript
tags: [JavaScript, js, fechas, utilidades, operaciones con fechas]
---
Hola en este post les mostraré un par de funciones en *JavaScript* que uso con frecuencia para el manejo de fechas.
<!--more-->
#### Fecha con formato

La primera función es para regresar una fecha con formato de  `dd-mm-yyyy` (*día-mes-año*), esta función recibe como parámetro un objeto de tipo *Date* y regresa un string con la fecha formateada.

``` js
function fechaConFormato(fecha) {
  var dd = fecha.getDate();
  var mm = fecha.getMonth() + 1;
  var yy = fecha.getFullYear();
  return (dd>9? dd:'0'+dd)+'-'+(mm>9? mm:'0'+mm)+'-'+yy;
}
```

La forma de usar esta función sería de la siguiente forma:

``` js
var miFecha = new Date();
var fecha = fechaConFormato(miFecha);
console.log('La fecha es :', fecha);
```

Salida o resultado del console.log es: `La fecha es : 07-07-2017`

#### Sumar segundos a una fecha

En esta función nos permite sumar segundos a una fecha, la función recibe dos parametros, el primero es un objeto de tipo fecha y el segundo parámetro es la cantidad de segundos, y esta nos retorna un nuevo objeto de tipo fecha con el resultado de la suma de los segundos a la fecha original.

``` js
function sumarSegundos(fecha,  segundos ) {
  var fechaNueva= new Date(fecha);
  fechaNueva.setSeconds(fechaNueva.getSeconds() + segundos);
  return fechaNueva;
}
```

También podemos sumar *minutos*, *horas*, *días*, etc. haciendo la debida conversión y la forma de usar es así:

``` js
var miFecha = new Date(); //Fecha original: 2017-07-07T23:30:51.607Z
var segundos = 30;
var minutos = 7*60;
sumarSegundos(segundos); //Resultado: 2017-07-07T23:31:21.607Z
sumarSegundos(minutos); //Resultado: 2017-07-07T23:37:51.607Z
```

***Próximamente seguiré actualizando este post añadiendo más funciones útiles.***

No te olvides de compartir y dejar tus comentarios, si quieres saber de algún tema más específico puedes dejarlo en los comentarios.

# Clean code y Deuda técnica

## Deuda Técnica

<ul>
    <li> <b style="font-style: italic;">Imprudente: </b> Proyecto con mala calidad, y poco tolerante al cambio.</li>
    <li><b style="font-style: italic;">Inadvertido: </b> Posiblemente generada por un Junior o un falso Senior.</li>
    <li> <b style="font-style: italic;"> Prudente: </b> Se tiene conocimiento, pero no se trata de forma inmediata.</li>
    <li> <b style="font-style: italic;"> Prudente e inadvertido: </b> Nos damos cuenta cuando ya se esta codificando la aplicación.</li>
</ul>

La deuda técnica se paga mediante la ***Refactorización***. Es simplemente un proceso que tiene como objetivo mejorar el código sin alterar su comportamiento para que sea mas entendible y tolerante a cambios, usualmente para que la refactorización tenga el objetivo esperado, es imprescindible contar con **Pruebas Automáticas.**
<br>
<hr>
<p align = "center" style="font-style: italic;"> La mala calidad en el software siempre la acaba pagando o asumiendo alguien. Ya sea el cliente, el proveedor o el propio desarrollador dedicando tiempo a refactorizar o malgastando tiempo programando sobre un sistema frágil </p>  
<br>
<p align = "center" style="font-style: italic;">Código limpio es aquel que se ha escrito con la intención de que otra persona (o tu mismo en el futuro) lo entienda <br>- Carlos Ble </p>  
<p align = "center" style="font-style: italic;">Nuestro código tiene que ser simple y directo, debería leerse con la misma facilidad que un texto bien escrito <br>- Grady Booch</p>
<p align = "center" style="font-style: italic;">Programar es el arte de decirle a otro humano lo que quieres que la computadora haga <br> - Donald Knuth</p>   
<hr>
<br>

## Nombres pronunciables y expresivos

No debemos ahorrar caracteres a la hora de nombrar las variables, debemos usar nombres expresivos.

| Mal       | Bien       |
------------|------------|
***const*** n     | ***const*** numberOfUnitis|
***const*** tx     | ***const*** tax|
***const*** cat     | ***const*** category|
***const*** ddmmyyyy     | ***const*** birthDate|

**Ausencia de información técnica en nombres** debemos de intentar que los nombres no contengan información técnica en ellos.

| Mal       | Bien       |
------------|------------|
***class*** AbstractUser     | ***class*** User|
***interface*** UserInterface     | ***interface*** User|


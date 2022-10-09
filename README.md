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
<p align = "center" style="font-style: italic;"> La mala calidad en el software siempre la acaba pagando o asumiendo alguien. Ya sea el cliente, el proveedor o el propio desarrollador dedicando tiempo a refactorizar o malgastando tiempo programando sobre un sistema frágil. </p>  
<br>
<p align = "center" style="font-style: italic;">Código limpio es aquel que se ha escrito con la intención de que otra persona (o tu mismo en el futuro) lo entienda. <br>- Carlos Ble. </p>  
<p align = "center" style="font-style: italic;">Nuestro código tiene que ser simple y directo, debería leerse con la misma facilidad que un texto bien escrito. <br>- Grady Booch.</p>
<p align = "center" style="font-style: italic;">Programar es el arte de decirle a otro humano lo que quieres que la computadora haga. <br> - Donald Knuth</p>   
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

## Consideración para los nombres de las Clases.

<ul>
    <li>El nombre es lo mas importante de la clase.</li>
    <li>Formados por un sustantivo o frases de sustantivos.</li>
    <li>No deben de ser muy genéricos.</li>
    <li>Usar UpperCamelCase</li>
</ul>

## Nombres de funciones

<p align = "center" style="font-style: italic;"> Sabemos que estamos desarrollando código limpio cuando cada función hace exactamente lo que su nombre indica. <br> -Warm Cunningham. </p>  
<ul>
    <li>Se recomienda limitar a 3 parámetros posicionales.</li>
    <li>Se recomienda que sean ordenados de forma alfabética.</li>
    <li>La simplicidad es fundamental.</li>
    <li>Funciones de tamaño reducido.</li>
    <li>Funciones de una sola linea sin causar complejidad.</li>
    <li>Menos de 20 lineas de código.</li>
    <li>Evitar el uso del "else", lo mas posible</li>
    <li>Priorizar el uso de la condición ternaria.</li>
</ul>

**Ejemplo** <br>
Mal -> **function** sendEmail( **toWhom**: string, **from**: string, **body**: string, **subject**: string, **apiKey**:string): boolean { ... }

Bien -> **function** sendEmail( {toWhom, from, body, subject, apiKey}: SendEmailOptions ): boolean { .. }

## Principio DRY (Don't Repeat Yourself)

<p align = "center" style="font-style: italic;"> Si quieres ser un programador productivo esfuérzate en escribir código legible. <br> -Robert C. Martin.</p> 

<ul>
    <li>Se debe de evitar tener duplicidad de código.</li>
    <li>Simplificar las pruebas.</li>
    <li>Ayuda a centralizar procesos.</li>
    <li>Aplicar el principio DRY, usualmente lleva a refactorizar.</li>
</ul>

# Clean Code - Clases y Comentarios
- Las clases deben de tener una responsabilidad única.
<br>

**Estructura Recomendada:**
<ul>
    <li>Propiedades estáticas.</li>
    <li>Propiedades publicas.</li>
    <li>Propiedades privadas.</li>
    <li>Constructores estáticos.</li>
    <li>Constructor.</li>
    <li>Métodos estáticos.</li>
    <li>Métodos privados.</li>
    <li>Métodos de instancia ordenados de mayor a menor importancia.</li>
    <li>Get y Set.</li>
</ul>

**Comentarios:**
<br>
 Evitar usar comentarios, pero...<br>Cuando usamos librerías de terceros, APIS, frameworks, etc. Nos encontraremos ante situaciones en las que escribir comentarios sera mejor que dejar una solución compleja o un hack sin explicación. **Los comentarios deberían ser la excepción, no la regla.**
 <p align = "center" style="font-style: italic;"> No comentes el código mal escrito, reescribirlo. <br> -Brian W. kernighan.</p>

 # Acrónimo - STUPID

 **Code Smells que debemos de evitar**
- **S**ingleton: Patron singleton.
- **T**ight Coupling: Alto acoplamiento.
- **U**ntestability: Código no probable.
- **P**remature optimization: optimizaciones prematuras.
- **I**ndescriptive Naming: nombres poco descriptivos.
- **D**uplication: Duplicidad de código, no aplicar el principio DRY.

**Código no probable**
- Código con alto acoplamiento.
- Código con muchas dependencias no inyectadas.
- Dependencias en el contexto global (Tipo Singleton).
<br>
Debemos de tener en mente las pruebas desde la creación del código.

**Duplicidad de código.**

Accidental | Real |
---|----|
Código que luce similar pero cumple funciones distintas. |Código que es idéntico y cumple la misma función.|
Cuando hay un cambio, solo hay que modificar un solo lugar. | Un cambio implicaría actualizar todo el código idéntico en varios lugares.|
Este tipo de duplicidad se pude trabar con parámetros u optimizaciones. | Incrementa posibilidades de error humano al olvidar una parte para actualizar. |
 | | mayor cantidad de pruebas innecesarias.|

**Otros olores honoríficos.**
<p align = "center" style="font-style: italic;"> Inflación - métodos.</p>
<p align="center">
  <img src="./assets/img/inflacion/inflacion.png" width="600">
</p>

<p align = "center" style="font-style: italic;"> Inflación - clases.</p>
 <p align="center">
  <img src="./assets/img/inflacion/class-inflacion.png" width="600">
</p>

<p align = "center" style="font-style: italic;"> Inflación - obsesión primitiva.</p>
<p align="center">
  <img src="./assets/img/inflacion/obsesion-inflacion.png" width="600">
</p>

<p align = "center" style="font-style: italic;"> Inflación - lista larga de parámetros.</p>
<p align="center">
  <img src="./assets/img/inflacion/parametros-inflacion.png" width="600">
</p>

<p align = "center" style="font-style: italic;"> Acoplador - Feautre envy.</p>
<p align="center">
  <img src="./assets/img/acoplador/feature-acoplador.png" width="600">
</p>

<p align = "center" style="font-style: italic;"> Acoplador - Intimidad inapropiada.</p>
<p align="center">
  <img src="./assets/img/acoplador/intimidad-acoplador.png" width="600">
</p>

<p align = "center" style="font-style: italic;"> Acoplador - Cadenas de mensajes.</p>
<p align="center">
  <img src="./assets/img/acoplador/cadena-acoplador.png" width="600">
</p>

<p align = "center" style="font-style: italic;"> Acoplador - The middle man.</p>
<p align="center">
  <img src="https://github.com/Jhoan-Dominguez/Principios_SOLID/blob/5158dd4d9c1171c703c7631482f422ec279362ee/assets/img/acoplador/cadena-acoplador.PNG" width="600">
</p>


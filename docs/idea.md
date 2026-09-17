# Exorsister

## Índice

1. [¿Qué es?](#1-qué-es)
2. [Gameplay loop](#2-gameplay-loop)
3. [Libro](#3-libro)
4. [Jefe final](#4-jefe-final)
5. [Mal del mundo](#5-mal-del-mundo)
6. [Vidas](#6-vidas)
7. [Jugador](#7-jugador)
8. [Mundo](#8-mundo)
9. [Combate](#9-combate)
10. [Inventario](#10-inventario)
11. [Equipamiento](#11-equipamiento)
12. [Estudio](#12-estudio)
13. [Clasificaciones](#13-clasificaciones)
14. [Energía y tiempo](#14-energía-y-tiempo)

---

## 1. ¿Qué es?

Exorsister es un juego de RPG por turnos de estilo roguelike.

El jugador podrá comenzar partidas, y bajo circunstancias determinadas podrá o ganar la run o perderla permanentemente. El progreso no se guarda entre partidas (explicación más adelante), sino que el jugador, al completar ciertos logros, desbloqueará objetos, personajes o mejoras permanentes para todas sus partidas. El objetivo del jugador es desbloquear todos los logros posibles y experimentar todos los eventos / objetos / enemigos.

## 2. Gameplay loop

Al comenzar el juego, la semilla de la partida (un número aleatorio) determinará TODOS los eventos, recompensas, enemigos y cosas que dependan de probabilidad (a excepción del combate, donde la probabilidad de golpear / esquivar / etc. sí es random).

- El juego no se pierde al morir, sino que este volverá a comenzar. El mundo tendrá la misma semilla, y el jugador experimentará los mismos eventos y recompensas.
- El jugador poseerá un libro, donde podrá guardar toda la información que quiera (más detalles adelante) y este libro será lo único que se guarda entre vidas.
- El jugador perderá la partida solo al morir al enfrentarse al jefe final (información adelante).

## 3. Libro

El libro es un objeto con el que el jugador comienza y no puede perder.

Este libro le permite al jugador escribir todo lo que quiera y guardarlo, y no se pierde entre vidas.

Lo que el jugador escriba es dejado para el jugador, pero el objetivo es permitir guardar información de los distintos descubrimientos de ese jugador durante la run. Por ejemplo, el jugador podrá guardar información de una misión, como su recompensa o método de victoria, para al comenzar otra vida poder hacerla con facilidad.

## 4. Jefe final

El objetivo del juego es vencer al jefe final. El juego contará con una barra de progreso, que al completarse invocará al jefe final y obligará al jugador a enfrentarlo.

- Esta barra de progreso persiste entre vidas, y es lo que obligará al jugador a hacer un plan rápidamente, ya que estará limitado por el tiempo que le toma a esta barra llegar al máximo (la barra NO sube en base al tiempo real, sino que el pasar de los días en el juego, que depende de las acciones del jugador, o distintos eventos, lo hará).
- El jefe depende de la semilla. El jugador deberá descubrir qué jefe es, cuáles son sus debilidades y fortalezas, con el fin de prepararse con antelación.
- El jugador tendrá la opción de, con la información de cómo invocarlo y los distintos objetos, invocar al jefe final por su cuenta. El jefe será más fuerte dependiendo de la barra de progreso, por lo que al esta llegar al máximo, el jefe estará en su punto más fuerte, pero si el jugador lo logra invocar prematuramente este será más débil, por lo que el jugador tiene la opción de hacerlo si piensa que está en un punto que puede derrotarlo. (Todos los objetos e información deben estar disponibles en la semilla, pero el jugador deberá descubrir tanto los objetos necesarios, el ritual y las reglas para ejecutarlo).
- El jefe final será el “mal del mundo”, más información adelante.

## 5. Mal del mundo

El mal del mundo es una mecánica especial que afecta las partidas.

El mal del mundo es un grupo de mecánicas que afectan la partida entre vidas, y es lo único, además del jefe, que cambia entre vidas. El mal del mundo es elegido secretamente entre un grupo al comienzo de la partida, y este afecta de distintas maneras, por ejemplo:

- **Mal carmesí:** al subir la barra, podrán aparecer enemigos poderosos alrededor del mundo, por lo que estos podrán tomar al jugador por sorpresa.
- **Mal de dinero:** los precios de los objetos pueden cambiar entre vidas, afectando los planes del jugador.
- **Mal de conocimiento:** el libro del jugador puede ser afectado, borrando o cambiando cosas sin avisarle al jugador.

Este mal será elegido aleatoriamente, y el jefe final deberá representar el mal en sí. Por ejemplo, el jefe del mal de dinero, por más de que el jefe sea generado aleatoriamente, deberá tener una mecánica que afecte / dependa del dinero, ejemplo:

- **Mal de conocimiento:** el jefe puede robar / restringir hechizos del jugador.
- **Mal carmesí:** el jefe puede invocar una gran cantidad de enemigos / sacrificar enemigos para ganar poder.

Los efectos del mal del mundo podrán ser encontrados como recompensas de misiones o si el jugador decide investigar (explicación más adelante).

## 6. Vidas

Las vidas de un jugador son independientes de la partida y dependen de la semilla. Como se explicó, perder una vida no significa perder la partida, sino volver a comenzar la semilla.

Al llegar la vida a 0, el jugador muere y vuelve a comenzar inmediatamente. Este solo mantendrá los conocimientos que guarde en el libro y recuerde, y todos los objetos / dinero / misiones que haya conseguido / realizado desaparecerán de su inventario, pero estas seguirán estando donde el jugador las encontró, por lo que, si el jugador recuerda cómo hacerlo, podrá volver a conseguir todo lo que tenía.

El jugador tiene vidas infinitas (aunque en dificultades más altas estas podrían estar restringidas). La única penalización por morir es el aumento del medidor del jefe y el hecho de volver a comenzar.

## 7. Jugador

El jugador contará con distintas estadísticas / habilidades / peculiaridades únicas de cada personaje, que se elige antes de comenzar la partida.

### Estadísticas

- **Vida máxima:** muestra la vida del jugador y su límite de vida.
- **Espíritu / Mente:** un recurso que sirve para distintas cosas, como coste para hechizos. También cuenta como una segunda barra de vida, ya que al recibir daño de esta estadística y esta estar en cero esto se verá reflejado en la vida en su lugar.
- **Energía en combate:** un número que muestra el número de acciones que el jugador puede ejecutar en un turno.
- **Energía fuera de combate:** muestra la cantidad de acciones (más información adelante) que el jugador puede hacer FUERA del combate antes de pasar de día.

### Habilidades

El jugador deberá tener dos tipos de habilidades principales: físicas y mentales.

- **Habilidades físicas:** estas habilidades dependen del personaje y los equipamientos que tengan. Estas no suelen tener un coste de mente y son ataques que el jugador podrá ejecutar con sus armas. Equipar distintos tipos de armas le dará acceso al jugador a distintos ataques. Estas gastan acciones definidas por el ataque.
- **Habilidades mentales:** estas habilidades dependen de los hechizos / maldiciones que el jugador conozca. Estas le permiten al jugador utilizar su mente para hacer diferentes tipos de efectos. Las habilidades mentales requieren de la habilidad “hablar” para ser usadas.

### Acciones en combate

- **Hablar:** es una mecánica que le permite al jugador escribir algo en texto. Este tendrá un límite de tiempo para escribir algo, y al terminar este tiempo o el jugador tocar Enter el personaje dirá la palabra (no relacionado con el audio), y si esa palabra es el nombre de un hechizo, entonces lo ejecuta. Hablar consume acciones, pero esto depende del tiempo que tome escribir, por ejemplo: al tomar 3 segundos esto consume una acción, los siguientes 3 segundos otra acción, y así hasta que el jugador se quede sin acciones, entonces al pasar los últimos 3 segundos el personaje se verá obligado a decir lo que escribió. Esta mecánica recompensa al jugador que recuerda sus hechizos y los escribe bien, pero si este escribe mal o pierde tiempo este perderá acciones sin realizar ninguna habilidad.
- **Consultar libro:** esto le permite leer su libro sin gastar ninguna acción. Así puede consultar los hechizos que haya guardado.
- **Cambiar equipo:** el jugador podrá cambiar su equipamiento en el medio del combate gastando acciones.

### Inventario y equipo

El jugador tendrá un inventario donde guardará objetos que se encuentre durante la partida. Este puede tener cualquier número de objetos, y tendrá espacios para equipárselos (sin coste fuera del combate).

Los espacios incluyen:

- **Casco:** otorga resistencia generalmente ligera y efectos tanto positivos como negativos.
- **Pechera:** otorga, generalmente, más resistencia y efectos que los cascos.
- **Manos:** el jugador tendrá dos espacios de manos. En cada una, este puede llevar un arma (a menos que el arma equipada requiera las dos manos) y 4 anillos en cada mano. Los anillos otorgan estadísticas y efectos mucho menores que los cascos y pecheras debido a la cantidad que se puede llevar.

### Peculiaridades / habilidades pasivas

El personaje contará con habilidades pasivas / peculiaridades especiales por cada personaje. Estas no son controladas por el jugador y afectan la manera en la que juega / sus estadísticas / etc. Estas pueden ser tanto positivas como negativas, y no pueden ser removidas.

Ejemplos de habilidades pasivas:

- **Frágil:** el personaje recibe más daño cuerpo a cuerpo.
- **Fuerte:** el personaje inflige más daño cuerpo a cuerpo.
- **Saludable:** el personaje recupera vida cada vez que gana una batalla.
- **Espiritual:** el personaje hace más daño con hechizos, pero menos daño con ataques cuerpo a cuerpo.

También existirán pasivas que afecten directamente a cómo el personaje juega el juego, y sus efectos son más radicales, como por ejemplo:

- El personaje utiliza vida en vez de mente para utilizar hechizos.
- El personaje solo puede utilizar un arma, pero esta hace el doble de daño.
- **Arma favorita:** el jugador NO puede cambiar de armas una vez que se equipa una, pero inflige más daño.

Hay que tener en cuenta que debe ser difícil tanto ganar habilidades pasivas como perderlas. Estas, al ser físicas / mentales, sus cambios no persisten entre vidas, lo que significa: el jugador comienza con determinadas pasivas, y cada vez que muere recibe estas mismas pasivas. El jugador, aunque gane o pierda estas pasivas, al morir regresará a tener las que originalmente tenía.

### Maldiciones / Efectos de estado

Las maldiciones y efectos de estado son similares a las habilidades pasivas. Estas otorgan beneficios y desventajas, con la diferencia de que son mucho más comunes de utilizar.

Los efectos de estado y maldiciones se diferencian en que las maldiciones SÍ persisten entre vidas.

#### Efectos de estado

Los efectos de estado son efectos físicos, como heridas o estados, por lo que no persisten entre vidas.

Existen dos tipos de efectos de estado: permanentes y temporales.

**Efectos de estado temporales:** estos efectos duran por un combate o determinada cantidad de tiempo, algunos ejemplos:

- **Veneno:** el personaje pierde vida al comienzo del turno, dura un combate.
- **Cansado:** el personaje tiene menos energía máxima, dura un día.

**Efectos de estado permanentes:** estarán activos indefinidamente hasta que el jugador los remueva, por ejemplo:

- **Pulmón perforado:** el personaje tiene menos energía máxima. Se cura en el hospital.
- **Hombro dislocado:** el personaje inflige menos daño. Se cura en el hospital.

#### Maldiciones

Las maldiciones son efectos permanentes, similares a las habilidades pasivas, que dan efectos especiales, pero se diferencian por el hecho de que estas sí persisten entre vidas. Las maldiciones no necesariamente son completamente negativas, pero en caso de que estas tengan un efecto positivo, también deberán tener uno negativo. Ejemplos:

- **Sed de sangre:** el personaje no puede hablar pero inflige más daño.
- **Sin voz:** el personaje no puede hablar.
- **Manos atadas:** el personaje solo puede llevar un arma.
- **Putrefacción:** el personaje pierde vida cada vez que utiliza una acción.

Estas maldiciones pueden ser removidas con distintos métodos.

## 8. Mundo

> A revisar.

La principal localización del juego es la casa. En esta, el jugador podrá dormir, recibir misiones (explicación más adelante) y crear / guardar objetos, entre otras cosas.

### Mecánicas principales de la casa

- **Dormir:** el jugador debe ser capaz de pasar el día / tiempo para recuperar energía para explorar el mundo.
- **Utilizar objetos:** el jugador podría utilizar objetos, como bebidas o comidas para aumentar / recuperar energía.
- **Teléfono:** el jugador podría comprar comida / objetos a domicilio para consumir o guardarla para luego.
- **Hacer ritual:** permite al jugador invocar al jefe si tiene los objetos necesarios.
- **Correo:** el jugador recibirá recompensas / misiones por correo.
- **Etc.:** más mecánicas explicadas luego.

### Estructura del mundo

El mundo no es mundo abierto, sino que le permitirá al jugador ir a distintos lugares para realizar distintas acciones. Este mundo es una ciudad donde está la casa del jugador.

Las localizaciones se distinguen entre “localizaciones fijas” y “puntos de evento”.

#### Localizaciones fijas

Estos son puntos donde el jugador puede ir a realizar acciones específicas. Estos siempre están ahí y el jugador irá con el mismo objetivo, consumiendo energía del día. Por ejemplo:

- **Hospital:** el jugador puede pagar dinero para removerse efectos de estado.
- **Tienda:** el jugador puede comprar objetos. Se diferencia del delivery al tener más cantidad y calidad, pero requiriendo energía ir a comprar.
- **Biblioteca:** el jugador puede utilizar energía para investigar, ver nuevos hechizos, aprender sobre enemigos, etc.

#### Puntos de evento

Los puntos de evento son localizaciones sin fines específicos más que el de contener eventos randoms y misiones. Ejemplos de estos pueden ser localizaciones como una plaza, un cementerio, el bosque. El jugador puede ir cuando quiera utilizando tiempo, pero mientras un evento esté ocurriendo o tenga una misión, en este lugar pueden aparecer enemigos u objetos. En estos lugares el jugador puede explorar las habitaciones (botón de explorar) o ir a otras partes del lugar (botón de moverse). Las habitaciones pueden tener objetos, y cada habitación tiene un número de veces que puede ser buscada.

## 9. Combate

El combate comienza cuando el personaje jugable se enfrenta a un enemigo. Este es un combate por turnos entre el jugador y el enemigo. El combate finaliza cuando el jugador o el enemigo muere, o cuando el jugador cumpla alguna condición especial del enemigo (explicado en enemigos).

- El primer turno siempre es del jugador, y solo termina cuando este no tiene energía o cuando este decida.
- Luego, será el turno del enemigo, y cuando este realice sus acciones comenzará el del jugador.
- Terminar un combate le dará al jugador recompensas basadas en el enemigo que derrotó.
- No puede haber más de un enemigo por combate.

### Enemigos

Los enemigos son los diferentes monstruos / entidades que el jugador deberá enfrentar durante la partida. A diferencia del jugador, estos no tienen ninguna estadística ni equipamiento.

Los enemigos tienen distintas partes del cuerpo que el jugador puede atacar. Estas partes tienen su propia vida y pueden ser destruidas, esto afectando de distintas maneras al enemigo. Cada parte del enemigo tiene su propia vida y estos no cuentan con una barra de vida total.

Ejemplos:

- Si el enemigo fuera un humano, destruir su brazo limitaría la cantidad de ataques que puede realizar, mientras que destruir su cabeza o pecho lo mataría instantáneamente.
- Si el enemigo fuera un monstruo, el jugador debería intentar conocer cuál es su punto débil, y qué utiliza para atacar.

Esto permite al jugador tener distintas opciones durante el combate. Intentar destruir la mayor parte del cuerpo del enemigo tomará más tiempo, pero será más seguro. Por otro lado, ir directamente por el punto débil es más arriesgado si el jugador no puede destruirlo rápido, pero en caso de que lo haga este será recompensado con una batalla más corta.

## 10. Inventario

El personaje contará con un inventario de infinito (?) espacio. En este almacenará todos los objetos que encuentre.

El jugador podrá acceder a su inventario en todo momento, pero si lo hace durante el combate, utilizar objetos de combate u equiparse objetos le costará acciones de combate.

Los objetos de combate son objetos de uno o varios usos que dan beneficios durante el combate.

## 11. Equipamiento

Los objetos equipables se encontrarán en misiones, tiendas y como recompensa de batalla. Estos serán generados aleatoriamente al comienzo de la run, teniendo distintas estadísticas y habilidades.

Al ser los objetos random, el jugador NO conocerá sus estadísticas ni habilidades al encontrarlos como recompensa de batalla y misiones, pero sí al comprarlos de tiendas. Esto incluye tanto objetos de batalla como objetos equipables. El jugador podrá descubrir las estadísticas, habilidades y clasificación del arma en el estudio (explicado más adelante).

Las armaduras y armas cuentan con distintas estadísticas base, más efectos que pueden añadir al jugador.

- **Armaduras:** dan distintos tipos de resistencias al jugador.
- **Armas:** dan un tipo de daño y habilidades físicas para que el jugador utilice (estas no son random y dependen del tipo de arma).
- **Efectos extra:** las armas y armaduras pueden tener efectos pasivos, tanto positivos como negativos, que afecten o al jugador o al enemigo.
- **Habilidades extra:** tener un arma equipada puede darle acceso al jugador a habilidades especiales mágicas que no requieren el habla para utilizar. NO todas las armas poseen estas habilidades, sino una minoría.

Para la generación de objetos se utilizará un algoritmo que, basado en ciertas calificaciones, dará un número de puntos y tipo de efectos. El juego le dará al arma ventajas (tienen un coste de puntos) y desventajas (disminuye el coste de puntos del arma, pero no todas las armas tendrán desventajas) y generará el arma.

- Los efectos positivos podrán variar de otorgarle al jugador regeneración, inmunidad a un tipo de daño, matar instantáneamente a enemigos que cumplan ciertas características, etc.
- Los negativos podrán restringir las acciones del jugador, disminuir su daño, aumentar el daño recibido, etc. Estos efectos negativos están ligados al arma y no se pueden remover, pero el jugador solo los sufrirá al utilizar el objeto.

## 12. Estudio

El jugador podrá enviar sus objetos al “estudio”, donde, luego de unos días, serán devueltos con una descripción de sus habilidades y estadísticas. Este proceso requiere que el jugador vaya a una zona para enviar el objeto (un correo, por ejemplo), consuma energía y el objeto podrá tardar días en volver. Una vez que el jugador envía y recibe de vuelta el objeto este, por todas sus vidas, podrá ver sus estadísticas, además de que el libro guardará la información automáticamente.

## 13. Clasificaciones

Las clasificaciones son tanto una mecánica como una parte real del universo del juego. Una clasificación es un número del 0 al 5, incluyendo un decimal, que sirve para mostrar el poder de algo. Este número, dentro del código, es asignado a todos los objetos, y este es el número que permite balancear los objetos dependiendo de su nivel, siendo más alto el nivel más poderoso el objeto.

La clasificación no solo existe para los objetos, sino también para los enemigos. Aunque todos los enemigos tengan una clasificación dentro del código, el jugador no podrá verla, sino que solo sabrá la calificación de enemigos que reciba en misiones. Esto le permitirá al jugador saber el nivel de dificultad de ciertas misiones antes de aceptarlas, pero no de otros enemigos que se verá obligado a enfrentar para deducirla.

La clasificación más baja es 0, y llega a un máximo de 5. 5 debe ser reservado solo para jefes que tengan una extrema dificultad y armas u objetos que sean casi imposibles de conseguir pero que casi garanticen ganar la partida al hacerlo.

La clasificación no solo se basa en estadísticas. Al los objetos poder tener desventajas, estos aumentarán su poder pero no su clasificación, un ejemplo de objetos con la misma clasificación pero diferente poder pueden ser:

- **Espada 1:** un arma que hace 100 de daño por golpe y no tiene habilidades. Clasificación 2.3.
- **Espada 2:** un arma que hace 200 puntos de daño, otorga una habilidad fuerte pero restringe al usuario de removérsela o utilizar hechizos. Clasificación 2.3.

En este caso, el arma 1 obtiene sus estadísticas base debido a su clasificación, mientras que el arma 2 tiene la misma clasificación, pero son las restricciones las que potencian su poder. Debido a esto, el arma 2 no debería ser considerada más fuerte, ya que es menos flexible y podría perjudicar al jugador, especialmente teniendo en cuenta que es posible el jugador no sepa sus efectos si no la envía a investigar.

Esto también se aplica a los enemigos, pero de distinta manera:

Para los enemigos, sus restricciones y debilidades sí afectan a su clasificación, ya que un jugador de bajo nivel con conocimiento puede derrotarlos.

- **Enemigo 1:** este enemigo tiene estadísticas normales para su clasificación. Clasificación 3.4.
- **Enemigo 2:** este enemigo tiene estadísticas por encima de su rango, pero tiene un punto débil o bajas resistencias. Clasificación 3.4.
- **Enemigo 3:** este enemigo tiene bajas estadísticas, pero un ataque que inflige un estado muy poderoso, este puede arruinar la partida del jugador, pero si este tiene conocimiento puede evitarlo fácilmente. Clasificación 3.4.

Además de las clasificaciones numéricas, existen ciertas calificaciones para las armas y enemigos.

### Clasificaciones especiales de armas

- **Arma maldita:** un arma que cuenta con una gran desventaja para aumentar el poder.
- **Arma sagrada:** un arma especial que cuenta con distintos efectos positivos pasivos sin perjudicar al usuario, pero con más restricciones. Un arma no puede ser tanto maldita como sagrada.
- **Arma básica:** un arma que solo cuenta con estadísticas y ningún efecto especial.
- **Arma mágica:** un arma que otorga al usuario habilidades mágicas por llevar el arma. Estas armas no tendrán desventajas, pero sus estadísticas serán generalmente más bajas que las de un arma base.

### Clasificaciones especiales de enemigos

- **Enemigo territorial:** un enemigo de alto nivel que aparece en una localización y nunca se mueve. Este enemigo debe ser fuerte, pero su existencia evitará que otros enemigos aparezcan en esa localización. Estos enemigos deberán “proteger” un objeto según el lore, por lo que darán mejores recompensas y siempre se encontrarán en un lugar que el jugador pueda acceder.
- **Enemigo fantasmal:** estos enemigos deberán aparecer solo de noche, y contarán con inmunidad a ataques físicos, pero debilidad a otros efectos.
- **Enemigos errantes:** enemigos que circulan por el mundo. Estos podrán atacar al jugador por sorpresa si este se los encuentra.
- **Enemigos especiales:** enemigos que pueden aparecer al jugador cumplir ciertas condiciones.
- **Enemigos relacionados al mal del mundo:** enemigos especiales con habilidades relacionadas al mal del mundo. Estos enemigos no se generarán al comienzo de la partida como todos los demás, sino que aparecerán alrededor del mundo dependiendo del nivel de maldad, para castigar al jugador y sorprenderlo si esta sube demasiado.

Las clasificaciones existen con el objetivo de que el jugador pueda tener un mayor entendimiento de los objetos y enemigos. Saber el tipo y clasificación del enemigo le ayudará a decidir si este es un enemigo que pueda derrotar, y le brindará información para tomar decisiones sin tener que enfrentarse a cada enemigo primero.

## 14. Energía y tiempo

Como ya se explicó, el jugador tiene energía fuera del combate que puede utilizar para realizar distintas acciones, generalmente ir a distintos puntos en el mapa. Esta energía no se recupera automáticamente, sino que al utilizar ciertos objetos o hacer ciertas acciones.

El tiempo, por otro lado, es el número de hora y el día. Ciertas acciones, además de energía, aumentan el tiempo. El tiempo no afecta el gameplay de ninguna manera que no sea influir en qué eventos / enemigos aparecen. Esto se debe a que, al generarse todas las misiones al comenzar una partida, el jugador las recibirá durante distintos días. Por lo que el jugador, al morir, comenzará en el día 1 y todas las misiones se reiniciarán. Los días también afectan a ciertos enemigos, por ejemplo, los enemigos fantasmales solo podrán aparecer en distintas horas del día.

El jugador puede dormir en su casa para recuperar energía a cambio de pasar el tiempo, pero en cualquier otra localización podrá descansar por una hora. Esto permite al jugador recuperar energía si lo necesita, sin tener que regresar, y pasar el tiempo, sin embargo, esta debe ser mucho menos efectiva que descansar en casa.

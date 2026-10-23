# Exorsister

RPG por turnos roguelike sobre descubrir y explotar el conocimiento de una partida.

## Language

**Partida**:
El ciclo completo sobre una semilla y un mal, desde el día 1 hasta vencer al jefe final o morir contra él.
_Avoid_: run, sesión, intento

**Vida**:
Un intento dentro de una partida. Al morir fuera del combate contra el jefe, se reinicia la misma semilla desde el día 1 conservando libro y barra del jefe; inventario, dinero y misiones vuelven a su origen.
_Avoid_: retry, reencarnación, intento

**Muerte de vida**:
La muerte fuera del combate contra el jefe final; termina la vida, no la partida.
_Avoid_: game over, permadeath

**Muerte de partida**:
La muerte contra el jefe final; termina la partida.
_Avoid_: derrota final, game over

**Libro**:
Objeto de la partida que sobrevive a sus vidas y se pierde al terminar la partida. El jugador escribe y consulta en él; no pertenece a la cuenta.
_Avoid_: diario, journal, cuaderno, notas

**Barra del jefe**:
Progreso de la partida que sobrevive a las vidas y, al llenarse, invoca al jefe final en su máximo poder. Se reinicia al terminar la partida.
_Avoid_: medidor, corrupción, doom clock

**Semilla**:
Valor que fija los eventos, recompensas, enemigos y misiones de una partida. El combate es la excepción: sus tiradas no están fijadas por la semilla.
_Avoid_: seed

**Mal del mundo**:
Modificador secreto elegido por partida que impregna el mundo y define la identidad del jefe final.
_Avoid_: corrupción, maldición global, curse

**Jefe final**:
El enemigo que representa al mal del mundo y cierra la partida: vencerlo la gana; morir contra él la pierde.
_Avoid_: boss, final boss

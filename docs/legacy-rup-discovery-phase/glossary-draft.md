# Domain Glossary — draft (Exorsister)

> Borrador de Inception. Se refina en `ooad-requirements`. Cada término referencia al menos una feature del PRD.

| Term | Definition | Synonyms to Avoid | Related | Rule / NFR | Source (PRD/FR/UC) |
|------|------------|-------------------|---------|------------|---------------------|
| Semilla | Número aleatorio que fija eventos, recompensas y enemigos de la partida; el combate usa RNG propio | seed suelta | Run, Vida | Determinismo 3/3 | F-001 |
| Run / Partida | Intento completo sobre una semilla; se gana venciendo al jefe, se pierde muriendo vs. jefe | run separada de vida | Vida, Jefe final | — | F-001, F-003 |
| Vida | Reintento dentro de la misma semilla tras morir (no-jefe); resetea inventario/dinero/misiones a su origen | intento, retry | Libro, Barra del jefe | Solo libro+barra persisten | F-001 |
| Libro | Objeto inicial imperdible donde el jugador escribe/consulta notas; persiste entre vidas; consulta gratis en combate | diario, journal | Estudio | Persistencia local | F-002 |
| Barra del jefe | Progreso persistente entre vidas que al llenarse invoca al jefe en su máximo poder; sube por días/acciones/eventos, no tiempo real | medidor, corruption | Jefe final, Ritual | — | F-003 |
| Jefe final | Enemigo que representa el mal del mundo, generado por semilla; vencible por invocación forzada o ritual prematuro (más débil) | boss, final boss | Mal del mundo | 2 vías de invocación | F-003 |
| Ritual | Acción en casa con objetos/información descubiertos para invocar al jefe prematuramente | invocación | Casa, Objeto | Objetos disponibles en semilla | F-003, F-010 |
| Mal del mundo | Modificador secreto por partida (carmesí/dinero/conocimiento) que altera vidas y le da mecánicas al jefe | corrupción, curse global | Jefe final | 1 mal mínimo en MVP | F-012 |
| Mal carmesí | Enemigos poderosos aparecen al subir la barra; el jefe invoca/sacrifica enemigos | — | Enemigo errante | — | F-012 |
| Mal de dinero | Precios cambian entre vidas; el jefe usa mecánica de dinero | — | Tienda | — | F-012 |
| Mal de conocimiento | Libro alterado sin aviso; el jefe roba/restringe hechizos | — | Libro, Hablar | Riesgo de confianza | F-012 |
| Vida máxima | Reserva de salud y su tope; cae a 0 = muerte de la vida actual | HP, salud | Mente | — | F-006 |
| Mente / Espíritu | Recurso para hechizos y segunda barra: daño a mente en 0 cae a vida | maná, MP | Hablar | — | F-006 |
| Energía en combate | Nº de acciones por turno; hablar consume 1 por cada 3s | AP, acciones | Hablar | — | F-004, F-006 |
| Energía fuera de combate | Nº de acciones (viajes/zonas) antes de pasar de día | — | Día, Tiempo | — | F-011 |
| Hablar | Mecánica de escribir el nombre del hechizo por teclado con límite de tiempo para ejecutarlo | cantar, decir | Hechizo | Solo texto, sin audio | F-006 |
| Habilidad física | Ataque del arma equipada, normalmente sin coste de mente | skill física | Arma | Tipo fijo por arma | F-006 |
| Habilidad mental / Hechizo | Efecto por mente ejecutado vía hablar | magia | Mente | Requiere hablar | F-006 |
| Pasiva / Peculiaridad | Rasgo del personaje no controlable ni removible; cambios no persisten entre vidas | perk, trait | Personaje | Reset a origen por vida | F-014 |
| Efecto de estado | Condición física temporal (veneno, cansado) o permanente (pulmón perforado) curable en hospital; no persiste entre vidas | status, debuff | Hospital | — | F-013 |
| Maldición | Efecto permanente con coste/beneficio que SÍ persiste entre vidas y es removible por métodos | curse | Pasiva | Tradeoff obligatorio | F-013 |
| Casa | Base con dormir/correo/ritual/objetos/telefono | hub, base | Ritual, Día | — | F-010 |
| Localización fija | Zona siempre disponible con acción específica (hospital/tienda/biblioteca) a coste de energía | shop genérico | Energía | — | F-010 |
| Punto de evento | Zona (plaza/cementerio/bosque) con eventos/misiones, habitaciones explorables con búsquedas limitadas | dungeon, mapa | Misión, Enemigo | — | F-010 |
| Combate por turnos | Encuentro 1v1 que inicia el jugador, termina por muerte o condición especial, da recompensa | batalla | Parte del cuerpo | Primer turno jugador | F-004 |
| Parte del cuerpo | Sección enemiga con vida propia destruible que altera al enemigo (p. ej. brazo→menos ataques; cabeza/pecho→muerte) | miembro | Punto débil | Sin barra total | F-005 |
| Objeto de combate | Consumible de 1+ usos con beneficio en combate, cuesta acciones | poción, item | Inventario | — | F-007 |
| Equipamiento | Arma/armadura generada por puntos; stats ocultos salvo tienda hasta pasar por estudio | loot, gear | Estudio | — | F-008 |
| Estudio | Envío por correo que tras días devuelve el objeto identificado y lo registra en el libro para todas las vidas | identificar | Libro, Correo | — | F-008 |
| Clasificación | Número 0–5 con decimal que expresa poder/base de balanceo; 5 reservado a jefes/objetos casi-garantía | rating, tier | Generador | 5 = extremo | F-009 |
| Día / Hora / Tiempo | Reloj que dispara eventos/enemigos y agenda de misiones; morir vuelve al día 1 y reinicia misiones | turno global | Energía fuera | No es tiempo real | F-011 |

## Discarded Terms

| Avoided Term | Use Instead | Reason |
|--------------|-------------|--------|
| HP/MP/AP | Vida máxima / Mente / Energía | Evitar jerga inglesa; usar lengua del PRD |
| Boss | Jefe final | Ubicuo en español en este dominio |
| Journal | Libro | Término canónico de la idea |
| Seed | Semilla | Ubicuo en español en este dominio |
| Sin voz (typo “Sin vos”) | Sin voz | Corrección de la idea §7 |

## Evolution Notes

- RUP: refinar por iteración; validar en `ooad-requirements` (cada término debe aparecer en ≥1 UC).

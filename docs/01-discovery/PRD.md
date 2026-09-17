# PRD: Exorsister

> Perfil: Iterative RUP (Inception). Fuente base: `docs/idea.md`. Plataforma MVP: PC, motor Godot (modo 3D).

## 1. Vision / Elevator Pitch

Exorsister es un RPG por turnos roguelike para jugadores de PC que disfrutan del conocimiento como progresión: cada partida queda fijada por una **semilla** que determina eventos, recompensas y enemigos; morir **no** pierde la partida, reinicia la misma semilla conservando solo el **libro** de notas y la **barra del jefe**. El objetivo es descubrir al **jefe final** (ligado al **mal del mundo** secreto), preparar el equipo/ritual y vencerlo antes de que la barra llegue al máximo — o invocarlo prematuramente más débil si el plan lo permite.

Por qué ahora: la idea ya detalla loop, combate, equipo y mundo; falta convertirla en baseline testeable (PRD → UC → C4 → slices) con un MVP de **run completa** en Godot 3D.

## 2. Users / Personas

| Persona | Goal | Current Pain |
|---------|------|--------------|
| Táctico roguelike | Ganar runs con builds distintas y dominio del sistema | Runs que se sienten random sin forma de aprender entre intentos |
| Explorador-anotador | Mapear semillas, misiones y debilidades en su libro | Juegos que no le dejan persistir su propio conocimiento |
| Cazador de jefes | Descubrir el mal del mundo e invocar al jefe en el momento justo | Jefes finales siempre iguales / sin decisión de timing |

Detalle en `docs/01-discovery/personas.md`.

## 3. KPIs / Success Criteria (measurable)

| KPI | Target | How Measured |
|-----|--------|--------------|
| Run completa jugable | 1 semilla fija ganable y 1 perdible (vs. jefe) de punta a punta | Playthrough guiado en build Godot PC |
| Determinismo de semilla | Misma semilla → mismos eventos/recompensas/enemigos en 3/3 reinicios | Test de reinicio tras muerte (no-jefe) ×3 |
| Combate 1v1 por turnos | 100% combates: primer turno jugador, 1 enemigo, recompensa al ganar | Checklist de combate ×10 encuentros |
| Libro persiste | Notas sobreviven a 3 muertes; inventario/dinero/misiones se resetean a su origen | Test muerte ×3 con lectura de libro |
| Jefe invocable 2 vías | Invocación por barra llena (máx. poder) y por ritual prematuro (débil) | 2 playthroughs, uno por vía |
| Rendimiento MVP | Sin caídas en escena casa + 1 punto de evento + combate en PC | Smoke test manual build PC |

## 4. Features (prioritized MoSCoW)

| ID | Feature | Priority | Rationale |
|----|---------|----------|-----------|
| F-001 | Semilla determinista + vidas/reinicio (muerte ≠ derrota, salvo vs. jefe) | Must | Núcleo del loop (§2, §6 idea) |
| F-002 | Libro persistente escribible/consultable (gratis en combate) | Must | Única persistencia entre vidas |
| F-003 | Barra del jefe persistente + jefe final por semilla + invocación ritual prematura | Must | Condición de victoria/derrota |
| F-004 | Combate por turnos 1v1, primer turno jugador, energía por acciones, recompensa | Must | Resolución central del juego |
| F-005 | Enemigos por partes del cuerpo con vida propia y puntos débiles | Must | Diferencial táctico del combate |
| F-006 | Jugador: vida/mente/energías + habilidades físicas/mentales + hablar (teclado, 3s/acción) | Must | Input firma del juego |
| F-007 | Inventario + equipo (casco/pechera/manos+anillos) + cambio en combate con coste | Must | Build y preparación |
| F-008 | Generador de equipo por puntos (ventajas/desventajas) + ocultamiento de stats + estudio por correo | Must | Economía de descubrimiento |
| F-009 | Clasificación 0–5 + especiales (armas: maldita/sagrada/básica/mágica; enemigos: territorial/fantasmal/errante/especial) | Must | Lenguaje de poder/decisión |
| F-010 | Casa (dormir/correo/ritual/objetos) + localizaciones fijas (hospital/tienda/biblioteca) + puntos de evento explorables | Must | Estructura del mundo no-abierto |
| F-011 | Energía fuera de combate + tiempo (día/hora) que dispara eventos y resetea misiones al día 1 | Must | Presión temporal del plan |
| F-012 | Mal del mundo secreto (carmesí/dinero/conocimiento) + jefe que lo representa | Must | Variedad entre partidas (1 mal mínimo en MVP) |
| F-013 | Efectos de estado temporales/permanentes + hospital; maldiciones persistentes removibles | Should | Profundidad de attrition |
| F-014 | Pasivas por personaje (incl. radicales: vida-por-mente, arma única, favorita) con reset a origen por vida | Should | Identidad de personaje |
| F-015 | Enemigos territoriales/fantasmales/errantes/especiales + relacionados al mal por nivel de maldad | Should | Vida del mundo |
| F-016 | Dificultades con vidas restringidas | Could | Tensión extra post-MVP |
| F-017 | Teléfono/delivery + consumibles de energía | Could | Comodidad vs. tienda |
| F-018 | Meta-logros con desbloqueables permanentes entre partidas | Won't (MVP) | Idea §1 lo pide, pero fuera del MVP single-run |

## 5. Out of Scope

- Multiplayer / cooperativo / rankings online.
- Meta-logros y desbloqueables permanentes entre partidas (se diseña para ellos, no se implementan en MVP).
- Voz/audio para “hablar” (solo texto por teclado); mundo abierto; guardado general entre partidas (solo libro + barra jefe).
- Plataformas distintas de PC; 2D u otro motor que no sea Godot 3D.

## 6. Assumptions / Risks

| Assumption | Impact if False | Mitigation |
|------------|-----------------|------------|
| Godot 3D rinde para escenas pequeñas (casa/localización) + UI texto | High | Escenas low-poly, UI Control nativa, smoke test temprano |
| Teclado PC disponible para “hablar” con límite 3s/acción | High | MVP solo PC; re-mapear a mando queda fuera de alcance |
| 1 mal del mundo basta para validar el loop en MVP | Medium | Diseñar males como datos (carmesí primero), añadir resto por iteración |
| Jugador acepta leer/escribir notas como progresión | Medium | Libro consultable gratis en combate; estudio auto-registra |
| Mal de conocimiento (editar/borrar libro) no rompe confianza en MVP | Medium | Solo 1 mal activo en MVP; tuneo en Elaboration |

## 7. Open Questions

- [ ] ¿Qué mal del mundo entra primero al MVP (carmesí propuesto)? → dueño: diseño → antes de RE
- [ ] ¿Cuántos personajes/pasivas mínimas para run completa (1–3 propuestos)? → dueño: diseño
- [ ] ¿RNG de combate con semilla separada o global? (idea: combate sí random) → dueño: tech
- [ ] ¿Formato de persistencia del libro en Godot (JSON/local)? → dueño: tech
- [ ] ¿Duración objetivo de run (nº días) para tuneo de barra del jefe? → dueño: diseño

## Approval

| Role | Date | Signature |
|------|------|-----------|
| PO/Stakeholder | | |
| Tech Lead | | |

# Agentic Second Brain

Claude arranca cada sesión sin saber quién sos, cómo trabajás ni dónde está lo importante. Agentic Second Brain lo corta: una carpeta de texto plano que lee al inicio, así deja de improvisar.

A diferencia de un segundo cerebro clásico, este casi no lo leés vos. Tu asistente trabaja desde él: tu contexto, proyectos, skills y rutinas en archivos de texto, para que el agente sepa qué cargar y cuándo.

Instalás un coach y arma el resto con vos, de a un escalón. Sirve en **Cowork** y **Claude Code**; **Codex** y otros agentes usan la misma carpeta vía `AGENTS.md`.

> **Idioma.** El coach habla en rioplatense (es la personalidad del método) y las carpetas base vienen con nombres en español que podés renombrar. Tu brain y tu contenido quedan en el idioma en que trabajes. README en inglés: [README.md](README.md).

---

## La diferencia se nota en la segunda sesión

La sentís la segunda vez que abrís Claude: ya no volvés a explicar el mismo contexto.

```text
Sesión 1, sin brain:
  Vos: soy diseñador freelance, mi stack es X, estoy con el rebrand de Acme,
       el tono va relajado... (cada sesión, de cero)

Sesión 2, con el brain:
  Vos:    redactá el mail de novedades de Acme
  Claude: (ya sabe quién sos, el proyecto, tu tono) Acá va un borrador...
```

Ese salto es todo el punto.

## El toolkit, listo el día uno

Estos no los armás vos. El plugin trae slash commands que funcionan apenas lo instalás, antes de configurar nada:

| Comando | Qué hace |
|---|---|
| `/asb` | El conserje: te lista las herramientas y te manda al coach |
| `/asb-slop` | Saca el olor a IA de un texto en una pasada |
| `/asb-write` | Redacta o reescribe en tu voz |
| `/asb-prompt` | Convierte un pedido crudo en un prompt listo para pegar en cualquier chat de IA |
| `/asb-panel` | 2 a 5 revisores con miradas distintas sobre algo antes de mandarlo |
| `/asb-council` | Un concilio de 5 asesores para una decisión con peso |
| `/asb-deck` | Arma una presentación por etapas, de bruto a final |
| `/asb-audit` | Chequeo de salud de tu segundo cerebro |
| `/asb-doc` | Cierra la sesión: rutea todo lo durable a su lugar |
| `/asb-simple` | ¿Perdiste el hilo? Estado en simple: dónde estamos, qué hacés vos, qué sigo yo |

Son herramientas de fábrica, sirven igual para todos. El coach (`/asb-coach`) arma la parte que es tuya: tus proyectos, tu identidad y tus propias skills. (Un *skill* es una receta guardada que dispara una frase. Usar estas es la forma más rápida de ver qué es uno antes de armar el tuyo.)

Corren como slash commands en Cowork y en Claude Code, sin configurar nada. En Cowork además las podés disparar describiendo lo que querés.

## Instalación

### Cowork (sin terminal)

1. En **Complementos personales** tocá el **+**, elegí **Crear plugin -> Agregar marketplace** y pegá: `brunogiel/agentic-second-brain`
   (atajo si podés escribir: `/plugin marketplace add brunogiel/agentic-second-brain`).
2. Instalá el plugin **agentic-second-brain**
   (o escribí `/plugin install agentic-second-brain@agentic-second-brain`).
3. Abrí o creá una carpeta donde quieras que viva tu brain (Drive, iCloud o Dropbox).
4. Usá uno de:
   - `/asb` (empezá por acá): el conserje, con tu toolkit y dónde vas parado
   - `/asb-coach`: el coach que arma tu sistema, te ubica y propone el próximo paso

El coach pregunta antes de crear archivos. No arma carpetas por atrás. En Cowork el plugin se actualiza solo.

### Claude Code

```bash
curl -fsSL https://raw.githubusercontent.com/brunogiel/agentic-second-brain/main/install.sh | bash
```

Instala el método y los comandos de forma global y no toca tu carpeta del brain. Después abrí la carpeta donde querés trabajar y escribí:

```text
/asb        # el conserje: tu toolkit + dónde vas parado (empezá por acá)
/asb-coach  # el coach: arma tu sistema, te ubica + propone el próximo paso
```

## Qué NO es

- **No es un cuaderno que leés vos.** A diferencia de Obsidian o Notion, el lector no sos vos. Es tu asistente.
- **No es un framework de dev.** Métodos tipo BMAD corren un build de software; esto guarda tu contexto de trabajo entero. Conviven.
- **No es Claude pelado.** Dejás de re-presentarte y re-explicar tus proyectos en cada sesión.

## Por qué funciona

El modelo genera texto. El cliente (Cowork, Claude Code, Codex) le da manos para leer y escribir archivos. Tu carpeta le da el contexto: quién sos, qué proyectos tenés, qué reglas seguir y dónde buscar. Tres ingredientes simples, sin magia.

## Qué se instala

Dos partes, separadas:

- **El método** vive fuera de tu carpeta. En Cowork es un plugin; en Claude Code vive en `~/.claude/skills/`. Ahí están el coach, las plantillas y el catálogo del kit.
- **Tu brain** vive en tu carpeta sincronizada, y guarda solo lo tuyo.

Tu carpeta del brain termina viéndose así:

```text
CLAUDE.md        # el router que tu asistente lee primero
ESTADO.md        # tablero corto, para retomar rápido
ESCALERA.md      # tu progreso + el catálogo del kit
AGENTS.md        # puntero para agentes no-Claude
0. Inbox/        # captura sin decidir
1. Proyectos/    # proyectos, una carpeta cada uno
2. Áreas/yo/     # quién sos, cómo trabajás, tu voz
3. Recursos/     # referencias reusables
4. Archivo/      # terminado o dormido
skills/          # los skills que activaste
```

El directorio `kit/` de este repo pertenece al método, no a tu brain: `kit/brain/` trae las plantillas de carpetas y `kit/skills/` el catálogo que el coach activa de a uno.

## Si ya tenés un sistema

No tenés que migrar. El coach mira tu estructura y la respeta.

La regla es simple: tiene que existir un router claro (`CLAUDE.md` o `AGENTS.md`) que diga dónde vive cada cosa. Si tu estructura ya funciona, el coach no la renombra ni te fuerza PARA. Solo propone mejoras puntuales: inbox, atajos, logs de decisión, skills o estado de sesión.

## Qué toca y cómo deshacerlo

- El instalador de Claude Code solo instala el método global.
- El coach crea archivos en tu brain solo si decís que sí.
- Si un archivo ya existe, no lo pisa.
- Las actualizaciones refrescan el método, no tu carpeta.
- Desinstalar borra el motor, no tus datos.

Para desinstalar en Claude Code:

```bash
curl -fsSL https://raw.githubusercontent.com/brunogiel/agentic-second-brain/main/uninstall.sh | SB_YES=1 bash
```

En Cowork, desinstalá el plugin desde la UI o escribí `/plugin uninstall agentic-second-brain`.

## La escalera

No armás todo el primer día. Subís de a un paso.

| Nivel | Qué armás | Para qué sirve |
|---|---|---|
| **0** | Identidad + inbox | El asistente sabe quién sos y no se pierden ideas sueltas |
| **1** | Primer proyecto con `CLAUDE.md` | No volvés a explicar contexto ni decisiones |
| **2** | Atajos frase -> carpeta | Decís "mis gastos" y sabe dónde mirar |
| **3** | Primer skill propio | Una frase dispara una receta que repetís |
| **4** | Rutina + herramienta conectada | El sistema puede leer mail, calendario o tareas |
| **5** | Orquestador | Varios skills trabajan juntos en una tarea |
| **6** | Auditoría y mejora | Revisás que el sistema no se degrade |
| **Si programás** | Código separado del contexto | El repo tiene código; el brain guarda decisiones |

El coach lee `ESTADO.md` y `ESCALERA.md`, te dice dónde estás y propone un solo próximo paso.

## Portabilidad

Tu brain son archivos de texto. Podés abrir la misma carpeta en Cowork, Claude Code, Codex o Cursor.

Los skills de uso viven en `skills/` y se activan desde la tabla **Mis skills** de `CLAUDE.md`. Codex y Cursor llegan a esa tabla por `AGENTS.md`. Lo único específico de Claude es el motor de armado: `/asb-coach` y, en Claude Code, `actualizar`. Si usás otro agente, `AGENTS.md` trae un fallback para operar el sistema a mano.

## Skills

La mayoría de las skills del kit son el toolkit de arriba, disponibles como comandos `/asb-*` desde el día uno. El coach además puede activar cualquiera como skill editable en tu propia carpeta `skills/` a medida que subís. Tres más no tienen comando, y el coach las suma cuando llegás a su nivel: `crear-skill` (armá el tuyo), `triage` (un brief del día con mail, agenda y tareas conectadas) y `evaluar-skill` (medí un skill contra su rúbrica).

## Filosofía

- Propone, vos decidís.
- Un paso por vez.
- Archivos chicos, leídos cuando hacen falta.
- Los skills duermen hasta que una frase los activa.
- Tu carpeta queda limpia: solo lo tuyo.

## Autor

Hecho por [Bruno Gielczynsky](https://www.linkedin.com/in/brunogiel/). Parte de una familia de métodos de AI instalables junto con [Empat.ia](https://github.com/brunogiel/Empat.ia).

## Licencia

MIT. Usalo, forkealo, hacelo tuyo.

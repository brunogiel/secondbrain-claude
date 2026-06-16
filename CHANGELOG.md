# Changelog

## 2.0.6
- `soul.md` pasa a ser una **hoja de personaje** (formato SOUL.md): identidad, verdades de base, cómo veo las cosas, voz y tono, límites. Define quién es el asistente cuando habla por vos, no solo tus valores pasivos. El coach ahora ofrece guardar también opiniones marcadas, voz y líneas que no se cruzan.

## 2.0.5
- Aclarado dónde viven los skills: los **generales** en `skills/` (raíz del SB), los **de un proyecto** en `1. Proyectos/<proyecto>/skills/`. No van en `3. Recursos/` (eso es referencia). Doctrina en `arquitectura-skills.md`.

## 2.0.4
- Los skills que arma el usuario ahora son **visibles**: viven en `skills/` de su carpeta (no más en el oculto `.claude/skills/`) y se rutean desde el `CLAUDE.md` raíz (sección "Mis skills"). El motor del kit (coach y demás) sigue global y oculto, que es la máquina.

## 2.0.3
- La doctrina de skills sale a la luz como **Recurso visible**: `3. Recursos/arquitectura-skills.md` (regla de 3, DET/LAT, anatomía, errores típicos, checklist). El `reference.md` oculto la resume y apunta ahí; el `crear-skill` la usa.

## 2.0.2
- Los skills del kit (el motor que usa el coach) van globales en `~/.claude/skills/`; los skills que el usuario arma quedan en `.claude/skills/` de su SB y viajan con él.
- README: el sistema es agnóstico al modelo y al harness (Claude Code, Cowork, Codex, Cursor, lo que venga). El cerebro son archivos de texto, portables.

## 2.0.1
- Footprint mínimo: la raíz queda con `CLAUDE.md` + `ESTADO.md`; los básicos de identidad (`sobre-mi`, `como-trabajo`, `mi-estilo`, `MEMORIA`) viven en PARA, en `2. Áreas/yo/`. `soul` y `dev-prefs` los suma el coach a medida que subís.

## 2.0.0
- Coach renombrado a `second-brain-coach`: es el punto de entrada único del sistema.
- Apertura en 3 modos (aprender / hacelo por mí / hacelo yo) + perilla de experiencia (en bolas / avanzado).
- El coach enseña el concepto de cada escalón, no solo te ubica.
- Onboarding: pregunta si ya tenés una carpeta de trabajo; si sí, la analiza y la adopta sin pisar nada.
- Escalera ampliada: se suma Nivel 4 (rutinas); el split código pasa a Nivel 5.
- Auto-update: tu primer skill es el chequeador de updates del kit (de paso aprendés qué es un script).
- Liviano para correr: el `CLAUDE.md` raíz pasa a router fino + `ESTADO.md` como tablero.
- Topología: el proceso vive oculto en `.secondbrain/`; a la vista quedan solo tus entregables.
- Templates nuevos: `soul.md` (se llena hablando) + `dev-prefs.md`.
- Skills-joya dormidos: `crear-skill`, `auditar-sistema`, `triage-mails`, `migrar-de-claude-projects`.
- Sirve al principiante y al avanzado (track "más allá" opt-in); pensado para Cowork, migra a Code.

## 1.0.0
- Versión inicial: PARA, super MD, `reference.md`, skills (coach / redactar / anti-slop), templates, `install.sh`.

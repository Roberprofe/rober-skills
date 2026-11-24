<p align="center">
  <img src="assets/logo.svg" alt="Logo de las skills, un pato blanco sobre fondo coral" width="236" height="236">
</p>

<h1 align="center">rober-skills</h1>

Dos skills en español para estudiar conceptos y depurar prácticas con un agente IA sin que haga el trabajo por ti.

| Skill | Para qué sirve | Archivo |
| --- | --- | --- |
| `rober-explica` | Entender un concepto desde la base, ver un ejemplo distinto al de tu práctica y saber qué documentación mirar. | [SKILL.md](skills/rober-explica/SKILL.md) |
| `rober-ayuda` | Acotar un error en código, redes, Linux, Windows o despliegue con una comprobación cada vez. | [SKILL.md](skills/rober-ayuda/SKILL.md) |

## Cómo funcionan

Estas skills no se activan solas: tienes que llamarlas por su nombre cuando las necesites.

Ninguna de las dos va a escribir tu entrega ni a tocar archivos de tu proyecto. Si insistes en pedir la solución directa, seguirán ayudándote a desbloquearte paso a paso en lugar de darte el código resuelto.

---

## Opción 1: Usarlas en chats web gratuitos (sin suscripción ni instalación)

Si usas **ChatGPT web**, **Gemini web**, **Claude web**, **Mistral**, **DeepSeek** o cualquier otro chat gratuito en el navegador, no necesitas instalar nada. Una skill es un archivo de texto Markdown que puedes pasarle al chat de tres formas:

### A. Copiar y pegar en un chat nuevo (la más rápida)

1. Abre el archivo de la skill que necesites: [rober-explica](skills/rober-explica/SKILL.md) o [rober-ayuda](skills/rober-ayuda/SKILL.md).
2. Pulsa el botón **Copy raw file** (arriba a la derecha en GitHub) para copiar todo el texto.
3. Abre un chat nuevo, pega el texto y añade tu consulta al final:

```text
Sigue estrictamente las instrucciones anteriores durante toda la conversación.

Mi duda es: [escribe aquí tu pregunta o tu error]
```

### B. Adjuntar el archivo `SKILL.md`

Sirve en cualquier chat que permita subir archivos (ChatGPT, Gemini, Claude, etc.):

1. Descarga el archivo `SKILL.md` de la skill que quieras usar.
2. Abre un chat nuevo, adjúntalo y escribe:

```text
Sigue estrictamente las instrucciones del archivo adjunto durante toda la conversación. Mi duda es: [escribe aquí tu pregunta o tu error]
```

### C. Guardarla una sola vez para reutilizarla

- **Gemini web (Gems):** puedes crear un Gem nuevo llamado *Rober Explica* y otro llamado *Rober Ayuda*, pegando en sus instrucciones el contenido del `SKILL.md` correspondiente. Así los tienes listos en la barra lateral sin repetir el proceso.
- **ChatGPT web (GPTs):** si tienes un enlace a un GPT que ya incorpora una de estas skills, puedes abrirlo directamente con tu cuenta gratuita.

**Consejo para chats web:** abre un chat nuevo cuando cambies de tema o de error. En conversaciones muy largas, los chats web acaban perdiendo de vista las instrucciones del principio.

---

## Opción 2: Instalarlas en agentes de terminal o editor

Si trabajas desde VS Code o la terminal con un agente compatible, puedes instalar las skills con `npx` (necesitas tener **Node.js** instalado). Ejecuta el comando desde la carpeta de tu proyecto.

Si quieres tenerlas disponibles en todos tus proyectos y no solo en una carpeta, añade `--global` al final del comando.

### Agentes con opción gratuita

**Gemini CLI** (cuota diaria gratuita con cuenta de Google):

```bash
npx skills add roberprofe/skills-aula --skill rober-explica --skill rober-ayuda --agent gemini-cli
```

**VS Code + GitHub Copilot** (plan Free):

```bash
npx skills add roberprofe/skills-aula --skill rober-explica --skill rober-ayuda --agent github-copilot
```

**OpenCode** (gratuito, compatible con modelos gratuitos o modelos locales con Ollama):

```bash
npx skills add roberprofe/skills-aula --skill rober-explica --skill rober-ayuda --agent opencode
```

**Cursor** (plan gratuito limitado) o **Cline** (extensión gratuita en VS Code):

```bash
npx skills add roberprofe/skills-aula --skill rober-explica --skill rober-ayuda --agent cursor
npx skills add roberprofe/skills-aula --skill rober-explica --skill rober-ayuda --agent cline
```

**Antigravity**:

```bash
npx skills add roberprofe/skills-aula --skill rober-explica --skill rober-ayuda --agent antigravity
```

### Otros agentes compatibles

**Codex** y **OpenCode** a la vez (puedes encadenar varios `--agent` en un mismo comando):

```bash
npx skills add roberprofe/skills-aula --skill rober-explica --skill rober-ayuda --agent codex --agent opencode
```

**Claude Code**:

```bash
npx skills add roberprofe/skills-aula --skill rober-explica --skill rober-ayuda --agent claude-code
```

**Hermes Agent** (instalación global en tu usuario):

```bash
npx skills add roberprofe/skills-aula --agent hermes-agent --global
```

### Instalación manual (si no tienes Node.js)

Si estás en un ordenador sin Node.js o con restricciones de red para `npx`, descarga las carpetas `skills/rober-explica` y `skills/rober-ayuda` de este repositorio y cópialas dentro de tu proyecto:

- En `.agents/skills/` si usas **Gemini CLI**, **GitHub Copilot**, **OpenCode**, **Codex**, **Cursor**, **Cline** o **Antigravity**.
- En `.claude/skills/` si usas **Claude Code**.

---

## Cómo llamarlas desde el agente

Una vez instaladas, abre el agente en tu proyecto e invócalas por su nombre (en algunos agentes también puedes escribir `/rober-explica` o `/rober-ayuda`):

- `Usa rober-explica para explicarme qué hace un ORM y cuándo tiene sentido usarlo.`
- `Usa rober-explica con este enunciado para entender qué conceptos necesito antes de empezar.`
- `Usa rober-explica para explicarme qué fue el Plan Marshall y por qué se puso en marcha.`
- `Usa rober-ayuda para acotar por qué mi contenedor no conecta con PostgreSQL.`

Si el agente tiene acceso web, abrirá y comprobará los enlaces de documentación oficial antes de pasártelos. Si no tiene conexión web, te dirá qué documentación y qué sección concreta buscar por tu cuenta.

---

[Formato Agent Skills](https://agentskills.io/specification) · [Comandos de instalación](https://github.com/vercel-labs/skills/blob/main/docs/commands.md) · [Agentes compatibles](https://github.com/vercel-labs/skills/blob/main/docs/agents.md)

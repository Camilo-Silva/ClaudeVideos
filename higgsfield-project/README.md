# Higgsfield AI Video Workflow

Automatización de generación de imágenes y videos con Claude Code + Playwright MCP en Higgsfield y Freepik.

## Requisitos

- Windows o Mac
- VS Code
- Chrome instalado
- Node.js ([descargar acá](https://nodejs.org))
- Cuenta en [Higgsfield](https://higgsfield.ai)
- Cuenta en [Freepik](https://freepik.com) (Premium+)
- Suscripción Claude Pro ([claude.ai](https://claude.ai))

## Instalación

### 1. Instalar Node.js
Descargar e instalar desde https://nodejs.org (versión LTS)

### 2. Instalar Claude Code
```bash
npm install -g @anthropic-ai/claude-code
```

### 3. Iniciar Claude Code y agregar Playwright MCP
```bash
claude
```
Dentro de Claude Code:
```bash
claude mcp add playwright npx '@playwright/mcp@latest'
```

**En Windows**, si aparece un warning sobre `cmd /c wrapper`, el comando queda configurado automáticamente.

Verificar que Playwright esté activo:
```bash
/mcp
```
Debe aparecer `playwright` con estado **connected**.

### 4. Clonar el repo y abrir en Claude Code
```bash
git clone https://github.com/Camilo-Silva/ClaudeVideos.git
cd ClaudeVideos/higgsfield-project
claude
```

Claude va a leer `CLAUDE.md` automáticamente y el workflow estará listo.

## Estructura

```
higgsfield-project/
├── CLAUDE.md          ← reglas y workflow (Claude lo lee automáticamente)
├── SESSION-RESUME.md  ← recuperación ante crashes
├── images/            ← imágenes generadas
├── videos/            ← videos generados
├── reference/         ← imágenes de referencia para personajes
└── output/            ← outputs finales
```

## Uso

Abrí Claude Code dentro de `higgsfield-project/` y escribí tu instrucción, por ejemplo:

```
Generate 1 image using NanoBanana 2. Follow CLAUDE.md workflow.
Prompt: Argentine mother 38 years old sitting with her son reading a book, 9:16
```

## Recuperación ante crash

Si Claude se cae a mitad de un batch:
```
Read SESSION-RESUME.md and continue from where we left off.
```

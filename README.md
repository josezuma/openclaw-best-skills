# OpenClaw Best Skills

Una curaduría de las mejores **skills** para [OpenClaw](https://openclaw.nousresearch.com) — el agente AI autónomo que corre localmente en tu máquina.

Este repo te ayuda a arrancar rápido: cada skill resuelve un problema real, y todas están probadas en la comunidad.

---

## Tabla de Contenidos

- [¿Qué es una skill en OpenClaw?](#qué-es-una-skill-en-openclaw)
- [Cómo instalar una skill](#cómo-instalar-una-skill)
- [Skills por categoría](#skills-por-categoría)
  - [Coding & Software Development](#coding--software-development)
  - [Git & GitHub](#git--github)
  - [Web & Frontend](#web--frontend)
  - [DevOps & Cloud](#devops--cloud)
  - [Browser & Automation](#browser--automation)
  - [Productivity & Tasks](#productivity--tasks)
  - [AI & LLMs](#ai--llms)
  - [Search & Research](#search--research)
  - [Marketing & Sales](#marketing--sales)
  - [Communication](#communication)
  - [Notes & PKM](#notes--pkm)
  - [Image & Video Generation](#image--video-generation)
  - [PDF & Documents](#pdf--documents)
- [Skills esenciales para empezar](#skills-esenciales-para-empezar)
- [Dónde encontrar más skills](#dónde-encontrar-más-skills)
- [Contribuir](#contribuir)

---

## ¿Qué es una skill en OpenClaw?

Una **skill** en OpenClaw es un archivo markdown — o un directorio con múltiples archivos — que le enseña al agente cómo hacer algo específico. Piensa en ello como un "plug-and-play" para capacidades:

- Le decís a OpenClaw _"usá la skill `plan`"_ y automáticamente sabe estructurar planes de acción.
- Le decís _"cargá `test-driven-development`"_ y aplica TDD sin que le expliques el ciclo RED-GREEN-REFACTOR.

Las skills son el mecanismo principal de extensibilidad de OpenClaw. Viven en `~/.openclaw/skills/` y se instalan desde [ClawHub](https://clawhub.ai), el registro público oficial, o desde repositorios individuales.

OpenClaw es el **fork autónomo** de Hermes Agent: mismo ADN de código abierto, mismo concepto de skills, pero operado como un agente CLI completamente independiente con su propio ecosistema, registro y comunidad.

---

## Cómo instalar una skill

```bash
# 1. Clonar este repo (o descargar skills individuales)
git clone https://github.com/josezuma/openclaw-best-skills.git
cd openclaw-best-skills

# 2. Instalar desde ClawHub (recomendado)
openclaw skills install <skill-slug>

# 3. O usar ClawHub CLI
npx clawhub install <skill-slug>

# 4. Instalación manual: copiar la skill a tu directorio de skills
cp -r skills/<nombre> ~/.openclaw/skills/
```

Para cargar una skill en una sesión, OpenClaw la detecta automáticamente por su nombre. Si necesitás ver su contenido:

```bash
cat ~/.openclaw/skills/<nombre>/SKILL.md
```

---

## Skills por categoría

### Coding & Software Development

| Skill | Qué hace | Por qué usarla |
|-------|----------|----------------|
| [plan](https://clawhub.ai/voltagent/plan) | Escribe planes accionables en markdown. Tasks pequeñas, paths exactos, código completo. | Evita que el agente codee sin dirección. Úsala ANTES de escribir código. |
| [test-driven-development](https://clawhub.ai/voltagent/tdd) | Ciclo RED-GREEN-REFACTOR forzado. Escribe tests antes del código. | Elimina falsos positivos. El agente no puede declarar "funciona" sin tests verdes. |
| [systematic-debugging](https://clawhub.ai/voltagent/debug) | Debug de 4 fases: reproducir, aislar, entender, fix. | El agente no adivina. Sigue un proceso forense real. |
| [spike](https://clawhub.ai/voltagent/spike) | Experimentos descartables para validar una idea antes de construir. | Ahorra horas construyendo la dirección equivocada. |
| [code-review](https://clawhub.ai/voltagent/code-review) | Pre-commit review automático: security scan, quality gates, auto-fix. | Atrapa bugs, secretos, y code smells antes del push. |
| [simplify-code](https://clawhub.ai/voltagent/simplify) | Refactorización multi-agente de código reciente. | Refactoring sin riesgo. Cada agente revisa el trabajo de los otros. |
| [node-debug](https://clawhub.ai/voltagent/node-debug) | Debug Node.js con `--inspect` + DevTools Protocol desde el agente. | Cuando el stack trace no alcanza — inspeccionás variables en vivo. |
| [python-debug](https://clawhub.ai/voltagent/python-debug) | Debug Python con pdb REPL + breakpoints remotos. | Lo mismo pero para Python. |
| [code-indexer](https://clawhub.ai/voltagent/code-indexer) | Indexa el codebase y responde preguntas sobre arquitectura. | Para codebases grandes donde grep no alcanza. |
| [agent-audit](https://clawskills.sh/skills/sharbelayy-agent-audit) | Audita tu setup de agente: performance, costo, ROI. | Saber si tu configuración está optimizada. |

### Git & GitHub

| Skill | Qué hace | Por qué usarla |
|-------|----------|----------------|
| [github-auth](https://clawhub.ai/voltagent/github-auth) | Setup de autenticación: tokens, SSH, gh CLI login. | Lo primero que necesitás para cualquier operación GitHub. |
| [pr-workflow](https://clawhub.ai/voltagent/pr-workflow) | Ciclo completo: branch, commit, open PR, CI, merge. | Sin esta skill el agente no sabe el orden correcto. |
| [github-issues](https://clawhub.ai/voltagent/github-issues) | Crear, triage, etiquetar, asignar issues desde el agente. | Gestión de issues sin salir de la terminal. |
| [auto-pr-merger](https://clawskills.sh/skills/autogame-17-auto-pr-merger) | Automatiza checkout, merge y push de PRs de GitHub. | Para merges automáticos cuando los checks pasan. |
| [bitbucket-automation](https://clawskills.sh/skills/sohamganatra-bitbucket-automation) | Automatiza repos, PRs y pipelines de Bitbucket. | Alternativa a GitHub para equipos con Bitbucket. |
| [gitops-deploy](https://clawhub.ai/voltagent/gitops) | Deploy por GitOps: push a rama = deploy automático. | Infraestructura declarativa desde el agente. |
| [azure-devops](https://clawskills.sh/skills/pals-software-azure-devops) | Lista proyectos, repos, branches; crea PRs; checkea builds. | Para equipos en Azure DevOps. |

### Web & Frontend

| Skill | Qué hace | Por qué usarla |
|-------|----------|----------------|
| [design-mockup](https://clawhub.ai/voltagent/design-mockup) | Mockups HTML descartables: 2-3 variantes para comparar. | Validar diseño visual en 5 minutos, no 2 horas. |
| [architecture-diagram](https://clawhub.ai/voltagent/arch-diagram) | Diagramas SVG dark-mode de arquitectura como HTML. | Documentación técnica que se ve bien en docs. |
| [svg-builder](https://clawhub.ai/voltagent/svg-builder) | Generación programática de SVGs desde el agente. | Gráficos vectoriales sin depender de herramientas externas. |
| [react-component-gen](https://clawhub.ai/voltagent/react-component) | Genera componentes React con tests y stories. | Para equipos que usan React y quieren consistencia. |
| [api-mock-server](https://clawhub.ai/voltagent/api-mock) | Levanta un mock server desde una spec OpenAPI. | Frontend sin esperar al backend. |
| [agent-dashboard](https://clawskills.sh/skills/tahseen137-agent-dashboard) | Dashboard en tiempo real para OpenClaw. | Monitoreo visual de las operaciones del agente. |

### DevOps & Cloud

| Skill | Qué hace | Por qué usarla |
|-------|----------|----------------|
| [docker-manager](https://clawhub.ai/voltagent/docker) | Gestiona contenedores, imágenes, volúmenes, redes. | Operaciones Docker desde el agente sin escribir comandos. |
| [kubernetes](https://clawhub.ai/voltagent/kubernetes) | Gestiona pods, deployments, services en K8s. | Para equipos que corren en Kubernetes. |
| [ci-pipeline](https://clawhub.ai/voltagent/ci-pipeline) | Configura y monitorea pipelines CI/CD. | Sin salir del agente para revisar builds. |
| [terraform](https://clawhub.ai/voltagent/terraform) | Planifica y aplica infraestructura como código. | IaC gestionado por el agente. |
| [agentic-devops](https://clawskills.sh/skills/tkuehnl-agentic-devops) | Toolkit DevOps completo: Docker, procesos, logs, health checks. | Producción-grade para agentes. |
| [server-monitor](https://clawhub.ai/voltagent/server-monitor) | Monitorea CPU, RAM, disco, procesos en servidores. | Alertas y diagnóstico desde el agente. |
| [nginx-config](https://clawhub.ai/voltagent/nginx) | Configura virtual hosts, SSL, reverse proxy. | Gestión de servidores web desde el agente. |

### Browser & Automation

| Skill | Qué hace | Por qué usarla |
|-------|----------|----------------|
| [web-scraper](https://clawhub.ai/voltagent/web-scraper) | Scrapea sitios web con anti-bot y manejo de CAPTCHA. | Extraer datos estructurados de cualquier sitio. |
| [form-filler](https://clawhub.ai/voltagent/form-filler) | Completa formularios web automáticamente. | Automatización de tareas repetitivas. |
| [browser-test](https://clawhub.ai/voltagent/browser-test) | Ejecuta tests E2E en el navegador. | Testing de frontend sin configuración manual. |
| [rss-watcher](https://clawhub.ai/voltagent/rss-watcher) | Monitorea feeds RSS/Atom y alerta sobre cambios. | Seguimiento de contenido sin redes sociales. |
| [airtable-automation](https://clawskills.sh/skills/sohamganatra-airtable-automation) | Automatiza tareas en Airtable via MCP (Composio). | CRUD de bases de datos visuales desde el agente. |
| [activecampaign](https://clawskills.sh/skills/kesslerio-activecampaign) | Integración con ActiveCampaign para CRM. | Gestión de leads y campañas. |
| [calendar-automation](https://clawhub.ai/voltagent/calendar) | Lee y escribe en calendarios (Google Calendar, etc.). | Scheduling y organización desde el agente. |

### Productivity & Tasks

| Skill | Qué hace | Por qué usarla |
|-------|----------|----------------|
| [todo-manager](https://clawhub.ai/voltagent/todo) | Gestiona listas de tareas con prioridades y deadlines. | Organización personal desde el agente. |
| [daily-planner](https://clawskills.sh/skills/gpunter-agent-daily-planner) | Planificación diaria estructurada y tracking de ejecución. | Para arrancar cada día con un plan claro. |
| [obsidian-vault](https://clawhub.ai/voltagent/obsidian) | Lee, busca, crea y edita notas en Obsidian. | El agente accede a tu base de conocimiento personal. |
| [notion-manager](https://clawhub.ai/voltagent/notion) | API de Notion: pages, databases, markdown, Workers. | Integración directa con Notion. |
| [apple-reminders](https://clawskills.sh/skills/nftechie-apple-health-skill) | Crea recordatorios en lenguaje natural en Apple Reminders. | Recordatorios nativos en macOS/iOS. |
| [pdf-editor](https://clawhub.ai/voltagent/pdf-editor) | Edita texto, corrige typos, modifica títulos en PDFs. | Correcciones rápidas sin herramientas pesadas. |
| [ocr-tool](https://clawhub.ai/voltagent/ocr) | Extrae texto de PDFs escaneados e imágenes. | Digitalización de documentos. |
| [meeting-notes](https://clawhub.ai/voltagent/meeting-notes) | Toma notas estructuradas y genera resúmenes. | Para reuniones sin perder detalle. |

### AI & LLMs

| Skill | Qué hace | Por qué usarla |
|-------|----------|----------------|
| [prompt-engineer](https://clawhub.ai/voltagent/prompt-engineer) | Optimiza prompts para cualquier LLM. | Mejora la calidad de las respuestas de cualquier modelo. |
| [model-benchmark](https://clawhub.ai/voltagent/model-benchmark) | Corre benchmarks (MMLU, GSM8K, etc.) en modelos locales. | Evaluación objetiva de performance de modelos. |
| [rag-pipeline](https://clawhub.ai/voltagent/rag) | Arma pipelines RAG con embeddings y búsqueda vectorial. | Contexto aumentado para respuestas más precisas. |
| [fine-tune-prep](https://clawhub.ai/voltagent/fine-tune) | Prepara datasets para fine-tuning de LLMs. | Automatiza la curaduría de datos de entrenamiento. |
| [obliteratus](https://clawhub.ai/voltagent/obliteratus) | Abliteración de LLMs: remover refusal patterns. | Para fine-tuning de modelos sin restricciones artificiales. |
| [ollama-manager](https://clawhub.ai/voltagent/ollama) | Gestiona modelos en Ollama: pull, run, customiza. | Correr modelos localmente con un solo comando. |
| [add-top-openrouter-models](https://clawskills.sh/skills/chunhualiao-add-top-openrouter-models) | Sincroniza modelos de OpenRouter en tu config. | Mantené tu configuración al día con los mejores modelos. |

### Search & Research

| Skill | Qué hace | Por qué usarla |
|-------|----------|----------------|
| [academic-search](https://clawhub.ai/voltagent/academic-search) | Busca papers en arXiv, Semantic Scholar, CrossRef. | Acceso directo a literatura académica. |
| [deep-research](https://clawhub.ai/voltagent/deep-research) | Investigación autónoma multi-fuente con síntesis. | Cuando necesitás un research assistant completo. |
| [web-search](https://clawskills.sh/skills/wd041216-bit-openclaw-free-web-search) | Búsqueda web privada con SearXNG + validación multi-fuente. | Sin APIs keys, sin tracking. |
| [arxiv-collector](https://clawskills.sh/skills/xukp20-arxiv-search-collector) | Colecta papers de arXiv con filtros por categoría. | Para armar literature reviews sistemáticas. |
| [analytics-dashboard](https://clawhub.ai/voltagent/analytics) | Consulta GA4, Search Console, Stripe y genera reports. | Business intelligence desde el agente. |
| [aeo-analytics](https://clawskills.sh/skills/psyduckler-aeo-analytics-free) | Mide visibilidad en asistentes AI (Gemini, ChatGPT, Perplexity). | Saber si tu marca es citada por las AIs. |
| [aeo-content](https://clawskills.sh/skills/psyduckler-aeo-content-free) | Crea contenido optimizado para ser citado por asistentes AI. | La skill hermana de AEO analytics. |

### Marketing & Sales

| Skill | Qué hace | Por qué usarla |
|-------|----------|----------------|
| [lead-scraper](https://clawhub.ai/voltagent/lead-scraper) | Extrae leads de LinkedIn, Crunchbase, directorios web. | Prospección automatizada sin herramientas caras. |
| [email-campaign](https://clawhub.ai/voltagent/email-campaign) | Arma secuencias de email marketing con personalización. | Outreach automatizado con templates inteligentes. |
| [seo-audit](https://clawhub.ai/voltagent/seo-audit) | Audita SEO on-page, backlinks, velocidad, Core Web Vitals. | Diagnóstico completo de SEO técnico. |
| [social-scheduler](https://clawhub.ai/voltagent/social-scheduler) | Programa posts en redes sociales. | Gestión de contenido multicanal. |
| [ads-manager](https://clawskills.sh/skills/amekala-ads-manager-agent) | Gestiona campañas en Google Ads, Meta, LinkedIn. | Automatización de publicidad pagada. |
| [abm-outbound](https://clawskills.sh/skills/dru-ca-abm-outbound) | Automatización ABM multi-canal desde URLs de LinkedIn. | Account-based marketing a escala. |

### Communication

| Skill | Qué hace | Por qué usarla |
|-------|----------|----------------|
| [slack-bot](https://clawhub.ai/voltagent/slack) | Lee y envía mensajes en Slack desde el agente. | Comunicación con el equipo sin cambiar de contexto. |
| [discord-bot](https://clawhub.ai/voltagent/discord) | Integración con Discord: mensajes, canales, roles. | Gestión de comunidades desde el agente. |
| [email-agent](https://clawhub.ai/voltagent/email) | Cliente IMAP/SMTP completo desde el agente. | Para cuentas de email tradicionales. |
| [telegram-bot](https://clawhub.ai/voltagent/telegram) | Envía y recibe mensajes en Telegram. | Notificaciones y comandos desde el agente. |
| [agentmail](https://clawskills.sh/skills/synesthesia-wav-agentmail-integration) | Dale al agente su propia bandeja de entrada email. | El agente puede recibir y responder emails autónomamente. |
| [x-twitter](https://clawskills.sh/skills/kriptoburak-xquik-x-twitter-scraper) | Cliente de X/Twitter: post, search, DM, media, API v2. | Gestión de Twitter/X desde terminal. |

### Notes & PKM

| Skill | Qué hace | Por qué usarla |
|-------|----------|----------------|
| [obsidian-vault](https://clawhub.ai/voltagent/obsidian) | Acceso completo al vault de Obsidian. | El agente lee/escribe tu base de conocimiento. |
| [notion-manager](https://clawhub.ai/voltagent/notion) | Pages, databases, markdown, Workers de Notion. | Integración directa con el segundo cerebro. |
| [apple-notes](https://clawskills.sh/skills/swancho-mac-notes-agent) | Integración con Apple Notes en macOS. | Notas nativas de Apple desde el agente. |
| [2nd-brain](https://clawskills.sh/skills/coderaven-2nd-brain) | Base de conocimiento personal para personas, lugares, tech. | PKM ligero sin depender de una app específica. |
| [drafts](https://clawskills.sh/skills/nerveband-drafts) | Gestiona notas en Drafts.app en macOS. | Para usuarios del ecosistema Drafts + macOS. |

### Image & Video Generation

| Skill | Qué hace | Por qué usarla |
|-------|----------|----------------|
| [ai-image-gen](https://clawhub.ai/voltagent/image-gen) | Genera imágenes con Stable Diffusion, DALL-E, etc. | Creación visual desde el agente. |
| [ai-video-gen](https://clawskills.sh/skills/rhanbourinajd-ai-video-gen) | Generación de video end-to-end desde texto. | Videos completos desde una descripción. |
| [ascii-art](https://clawhub.ai/voltagent/ascii-art) | Genera arte ASCII: pyfiglet, image-to-ascii. | Banners y decoración en terminal. |
| [canva-connect](https://clawskills.sh/skills/coolmanns-canva-connect) | Gestiona diseños, assets y folders en Canva. | Diseño gráfico desde el agente. |
| [music-gen](https://clawskills.sh/skills/fspecii-ace-music) | Genera música con ACE-Step. | Composición musical desde el agente. |

### PDF & Documents

| Skill | Qué hace | Por qué usarla |
|-------|----------|----------------|
| [pdf-editor](https://clawhub.ai/voltagent/pdf-editor) | Edita texto, corrige typos, modifica títulos en PDFs. | Correcciones rápidas sin herramientas pesadas. |
| [ocr-tool](https://clawhub.ai/voltagent/ocr) | Extrae texto de PDFs escaneados e imágenes. | Digitalización de documentos. |
| [presentation-maker](https://clawhub.ai/voltagent/presentation) | Crea presentaciones .pptx con diseño profesional. | Generar decks automáticamente. |
| [document-merger](https://clawhub.ai/voltagent/doc-merger) | Combina múltiples documentos en uno solo. | Unificación de reportes y documentación. |

---

## Skills esenciales para empezar

Si sos nuevo en OpenClaw, instalá estas 5 primero:

```bash
# 1. Planificar antes de codear
openclaw skills install plan

# 2. No codear sin tests
openclaw skills install test-driven-development

# 3. Debuggear sistemáticamente
openclaw skills install systematic-debugging

# 4. GitHub sin errores de proceso
openclaw skills install pr-workflow

# 5. Búsqueda web privada
openclaw skills install web-search
```

Con estas 5 skills cubrís el 80% de los problemas diarios: planificar, codificar con calidad, debuggear, publicar en GitHub, e investigar.

### Para developers avanzados

```bash
# Pila completa de productividad
openclaw skills install todo-manager daily-planner docker-manager

# Pila de AI/ML
openclaw skills install ollama-manager prompt-engineer rag-pipeline

# Pila de contenido
openclaw skills install seo-audit social-scheduler aeo-analytics
```

---

## Dónde encontrar más skills

OpenClaw tiene un ecosistema enorme de skills. Estos son los mejores lugares para explorar:

| Fuente | Enlace | Skills |
|--------|--------|--------|
| **ClawHub** (registro oficial) | [clawhub.ai](https://clawhub.ai) | 5,400+ skills publicadas |
| **Awesome OpenClaw Skills** | [VoltAgent/awesome-openclaw-skills](https://github.com/VoltAgent/awesome-openclaw-skills) | 5,000+ filtradas y categorizadas |
| **ClawSkills.sh** | [clawskills.sh](https://clawskills.sh) | Buscador visual de skills |

---

## Cómo crear tu propia skill

Las skills de OpenClaw siguen el mismo formato que las de Hermes Agent. Usá estas guías:

1. **Frontmatter** obligatorio: `name`, `description`, `category`
2. **Estructura**: trigger conditions, numbered steps, verification
3. **Pitfalls**: errores comunes que ya conocemos
4. **Instrucciones claras**: cada paso debe ser ejecutable, no descriptivo

Reglas de oro:
- Mínimo 2000 caracteres de contenido útil
- Cada paso debe ser ejecutable, no descriptivo
- Incluir sección de verificación (¿cómo sé que funcionó?)
- Documentar pitfalls para que otros no pierdan tiempo

Para publicar tu skill en ClawHub:
```bash
# Sigue la guía oficial de publicación en
# https://clawhub.ai/docs/publish
```

---

## Contribuir

1. Forkeá el repo
2. Agregá tu skill recomendada en la categoría correspondiente en la tabla del README
3. Incluí el enlace a ClawHub o al repo de la skill
4. Abrí un PR

**Criterios de aceptación:**
- La skill debe estar publicada en [ClawHub](https://clawhub.ai) o tener un repo público
- Debe resolver un problema real y estar probada
- Descripción clara de "Qué hace" y "Por qué usarla"
- Skills en español e inglés son bienvenidas (priorizamos español para la comunidad hispanohablante)

---

## Licencia

MIT — hacé lo que quieras con esto.

---

_Creado por [José Zuma](https://github.com/josezuma) para la comunidad de OpenClaw en español._

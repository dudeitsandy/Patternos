# Skill: Coding
# PatternOS | Andy Styx
# Load this when helping with any code task.

---

## Primary Stack

**Languages (in order of comfort):**
- Python — data engineering, automation, analytics, scripting
- SQL — star schema, dbt models, dimensional modeling
- JavaScript / HTML / CSS — frontend, single-file apps, vanilla first
- PowerShell — Windows automation, local tooling
- C# — Unity game development
- GDScript — Godot game development

**Data stack:**
- dbt, Databricks, Delta Lake, BigQuery, AWS
- Star schema / Kimball dimensional modeling — canonical preference
- Airflow for orchestration
- Pandas, NumPy for analysis
- SHAP, Cubist for ML explainability

**Frontend:**
- Vanilla HTML/CSS/JS as default — no framework unless complexity demands it
- Single-file architecture first (especially for MVPs and client demos)
- Chart.js for data visualization
- Tailwind for utility styling when needed
- React only when component complexity justifies it

**Deployment:**
- Netlify — drag and drop for static/single-file apps
- Railway — containerized services
- AWS — production infrastructure
- Docker — local dev environments (n8n, databases)

**AI / agent tooling:**
- Claude API, Claude Code (primary terminal agent)
- Cursor Pro, GitHub Copilot (IDE assistance)
- n8n (Docker, localhost:5678) for automation flows
- Together.ai for open model inference
- MCP servers for Claude Desktop integration

**Dev environment:**
- Windows / PowerShell primary
- Workspace root: `C:\Users\subfl\workspace\patternos`
- VSCode + Cursor
- Git / GitHub for version control

---

## Coding Philosophy

- Build the minimal thing that works before abstracting
- Single-file first — complexity earns its own files
- Prefer readable over clever
- Schema design before implementation — know your entities and relationships first
- Prototype to validate, then refactor for durability
- Ship imperfect working code over perfect unshipped code
- Comments explain why, not what
- Never add a dependency for something that can be done in 10 lines

---

## Output Standards

When producing code:
- Always include a brief comment block at the top: what this does, key dependencies, how to run
- Use meaningful variable names — no single letters outside of loop counters
- For data models: always show the full schema before the implementation
- For scripts: include a usage example in comments
- For HTML apps: self-contained single file unless told otherwise
- For Python: include requirements at the top as comments if not using a requirements.txt

---

## Project Patterns

**Ghostweave Intel (cannabis CRM):**
- Single-file HTML/CSS/JS, Chart.js, localStorage for field notes
- Deploys to Netlify via drag-and-drop
- No build step — vanilla only
- Data stored in Canada (Supabase Canada Central for any backend)

**CreatorOS (creator CRM):**
- Python backend, Telegram webhook, Together.ai API
- Playwright for headless browser platform integration
- RAG + dynamic system prompt architecture for voice modeling
- Windows dev environment, PowerShell venv activation

**PatternOS:**
- n8n (Docker) for automation
- Claude Desktop + MCP for interactive orchestration
- JSON context files as structured memory layer
- Railway for scheduled/webhook flows

---

## Rules

- On Windows: use PowerShell syntax, not bash, unless inside WSL or Docker
- Always confirm data storage location requirements before suggesting a backend (some clients require Canada)
- For people analytics work: always validate against star schema — worker and position are canonical entities
- When building for non-technical clients: single-file, no build step, drag-and-drop deploy
- Game dev in Unity uses C#. Game dev in Godot uses GDScript. Don't mix.
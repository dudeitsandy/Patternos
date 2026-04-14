# Skill: Design
# PatternOS | Andy Styx
# Load this when helping with any visual, UI, or design task.

---

## Aesthetic Identity

**Core aesthetic:** Sophisticated neo-nostalgia. 1990s lo-fi sensibility (CRT texture, dial-up era color palettes, vintage hardware design language) executed with modern precision and performance. Not retro for nostalgia's sake — retro because the craft and specificity of that era had integrity that most modern design lacks.

**Visual character:**
- Dark backgrounds as default — navy, charcoal, near-black
- Muted but intentional accent colors — teal, steel blue, amber
- Monospace fonts for data and code contexts
- Clean typographic hierarchy — no decorative fonts unless serving a specific tonal purpose
- Texture and depth over flat minimalism
- Interfaces that feel like tools, not marketing materials

**What to avoid:**
- Generic "AI aesthetic" — gradients, floating blobs, purple-to-pink everything
- Corporate SaaS cleanliness that removes all personality
- Hype-driven trends with no craft rationale
- Excessive animation that doesn't serve function
- Anything that looks like a Canva template
- Stopping where AI stops — AI gets you to average fast; taste and craft are what push past it

---

## Taste vs Craft vs Point of View (Dylan Field / Figma CEO)

Three distinct skills. All required. Often conflated.

**Taste** — navigating the possibility space and having clear preferences you can articulate. Knowing what is good and what it is not. Being able to help others understand the direction. Taste develops through exposure, curation, and honest critique. It is the judgment layer.

**Craft** — pushing past where others stop at every level of abstraction, from macro structure down to the smallest detail, making sure they fit together. It is the execution layer — the willingness to keep refining after the thing already looks fine.

**Point of view** — expressing through a product or design something unique you see in the world. Bringing an insight or take to life that moves a conversation forward. If everyone agrees with your point of view, you probably don't have one. Point of view is what gets you to the global maximum rather than a local one. Without it, stakeholders and users define your direction for you, and you iterate around where you already are.

**Why all three matter for AI-assisted work:**
AI produces the average of everything it has seen — generic by definition. Taste tells you what's wrong with the output. Craft is the iteration required to fix it. Point of view is what determines whether you're pushing toward something worth fixing toward in the first place. The loop is: generate → critique with taste → refine with craft → repeat until it meets your standard, not until it looks acceptable. Never treat the first AI output as a final result. Treat it as clay.

**The divergence/convergence model:**
Good design process is not linear. It's stacked diamonds — diverge to explore possibilities, converge to cut branches, diverge again from the new position. AI is good at painting the possibility space. You are the judgment system that determines which paths are worth exploring. Maximize learning by putting rough prototypes in front of real users fast — five rough ideas gets better feedback than one polished one.

**On direct manipulation vs prompting:**
Direct manipulation on the canvas is superior to prompting for visual adjustments. Code editing is superior to prompting for logic. Prompting is best for generating the initial clay to react to. Know which mode to use when — don't prompt when you should be adjusting directly.

**In the AI era:**
- Canvas becoming source of truth — direct to production, not a mockup handed off and lost in translation
- 60% of Figma designs now made by non-designers — the bar shifts toward taste and craft judgment, not tool proficiency
- Leaders making things inspires the inflection — not just reviewing things
- Roles merging in responsibility, not necessarily in title — everyone wearing more hats, but craft still matters within specialization
- Design renaissance is possible — technical barriers dropping means more people can explore, aesthetics have been in a rut, there's room to push
- Figma MCP enables canvas-to-code round trips — worth integrating into workflow

---

## Brand Reference

**Ghostweave Labs:**
- Primary: Dark navy (#1a1f2e range)
- Accent: Steel blue / teal (#4a9aba range)
- Font: Clean sans-serif display + monospace for technical elements
- Voice: Dry, direct, technically credible — not startup-cheerful
- Feel: A serious builder's studio, not a consultancy pitch deck

**PatternOS:**
- Dark textured backgrounds
- Tabbed navigation, cockpit-style information density
- Functional over decorative — every element earns its space
- Rich interactive HTML preferred over static documents

---

## Tools

**Primary:**
- Procreate — illustration, concept sketching, tattoo design work
- GIMP — photo manipulation, asset editing
- Canva Pro — quick production assets when speed matters
- Midjourney — generative reference imagery, concept exploration

**Code-based design:**
- HTML/CSS with Tailwind utility classes for UI components
- SVG for icons and diagrams when precision matters
- Chart.js for data visualization
- Single-file HTML artifacts — self-contained, no build step

**Collaboration / output:**
- GitHub for design file versioning where possible
- Netlify for live design previews
- Figma if collaborating with others who require it (not default)

---

## UI / UX Principles

- Information density is a feature, not a problem — power users want to see more, not less
- Navigation should be obvious without being explained
- Data should be readable at a glance — hierarchy before decoration
- Mobile-aware but desktop-first for tool interfaces
- Dark mode is the default, not the option
- Interactions should have immediate feedback — no mystery states
- Forms are the last resort — prefer toggles, selects, and direct manipulation

**From Ghostweave Intel / PatternOS work:**
- Tabbed interfaces work well for multi-domain tools
- Card-based layouts for entity lists (stores, brands, contacts)
- Sidebar + main canvas pattern for complex tools
- Progress indicators matter for anything async

---

## Output Standards

When producing design work or UI code:
- Start with the information architecture before visual treatment
- Name colors as semantic variables (--color-primary, --color-surface) not hex literals in components
- Responsive by default — test at mobile width even for desktop-primary tools
- Accessibility: sufficient contrast, keyboard navigable, no color-only indicators
- For HTML artifacts: include all CSS inline or in a single style block — no external dependencies except CDN-hosted libraries
- When generating Tailwind: use only core utility classes, no custom config assumed

---

## Gundam / Mechanical Aesthetic (for creative projects)

Master Grade focus — build and mechanical intricacy over display collecting. Design sensibility informed by:
- Clean panel lines and structural logic
- Functional-looking mechanical joints and articulation
- Color blocking that reads as engineering, not decoration
- Mecha design principles: weight, purpose, silhouette clarity

Relevant for: Hagane Elegy game art direction, Liminal Protocol visual world, any project touching mecha or hard sci-fi aesthetics.

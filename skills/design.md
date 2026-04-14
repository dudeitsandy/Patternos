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
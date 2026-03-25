# LLM Skills

Custom skill files for LLM coding agents. Each skill is a standalone `SKILL.md` that can be dropped into a compatible agent's skill directory.

## Skills

| Skill | Directory | What it does |
|-------|-----------|-------------|
| **Frontend Design** | `frontend/` | Opinionated frontend design system. Enforces intentional aesthetics, typography, and spatial composition over generic layouts. Includes a Design Feasibility & Impact Index (DFII) scoring model. |
| **Kaizen** | `kaizen/` | Continuous improvement principles for code. Covers incremental refactoring, error-proofing via types (Poka-Yoke), standardized patterns, and just-in-time implementation. |
| **Next.js Best Practices** | `nextjs-best-practices/` | App Router conventions. Server vs Client component decisions, data fetching strategies, caching layers, route organization, and server actions. |
| **Scroll Experience** | `scroll/` | Scroll-driven animation patterns. Covers GSAP ScrollTrigger, Framer Motion scroll, CSS `scroll-timeline`, parallax layering, sticky sections, and anti-patterns like scroll hijacking. |
| **SEO Audit** | `seo/` | Structured SEO diagnostic framework. Crawlability, indexation, Core Web Vitals, on-page optimization, E-E-A-T assessment, and a weighted 0–100 SEO Health Index scoring model. |

## Usage

Point your agent's skill directory to this repo, or copy individual skill folders into your existing setup. Each folder contains a single `SKILL.md` file with YAML frontmatter (`name`, `description`) followed by the full skill instructions.

## License

Community-sourced. See individual `SKILL.md` files for attribution.

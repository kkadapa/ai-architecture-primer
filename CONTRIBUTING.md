# Contributing

This primer is most valuable when it reflects real production experience, not just one person's view — so contributions from people actually fighting these architecture debates inside real organizations are especially welcome.

## Ways to contribute

- **Fix or update a cloud mapping** ([Section VII](sections/07-cloud-mappings.md)) — service names and tiers change fast; this is the lowest-friction, highest-value PR you can make.
- **Add or refine an industry walkthrough** ([Section VI](sections/06-industry-walkthroughs.md)) — if you've designed for a domain not covered yet (insurance, retail, manufacturing, public sector), a new walkthrough following the existing format is very welcome.
- **Challenge a "when to propose / when not to" call** — these are judgment calls, and the field is young enough that reasonable, experienced architects disagree. Open a discussion or issue explaining the production scenario that changes the guidance.
- **Add a new pattern** — if there's a recurring architecture this primer is missing, open an issue first to discuss scope before submitting a full section.
- **Fix diagrams** — all diagrams are Mermaid, rendered natively by GitHub. Keep the same visual style (teal for data/knowledge resources, purple for compute/reasoning components, gray for plain input/output or deterministic steps) for consistency across sections.

## Guidelines

- Keep the three-part structure (when to propose / what to get right / when not to use) for any new pattern — it's the core teaching device of this primer.
- Cite a real production source or your own deployment experience where you can, especially for claims about cost, latency, or failure modes.
- Stay vendor-neutral in Sections I–VI. Vendor specifics belong only in Section VII.
- Keep diagrams as Mermaid in-markdown, not external image files — this keeps them diffable in PRs and avoids broken image links.

## Opening a PR

1. Fork the repo
2. Make your change in a feature branch
3. If you touched a diagram, confirm it renders correctly in GitHub's Markdown preview before opening the PR
4. Open the PR with a short rationale — what changed and why

Small, focused PRs are easier to review and merge than large ones. If you have a big idea (a new section, a major restructure), open an issue to discuss it first.

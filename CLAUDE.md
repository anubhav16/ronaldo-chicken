# Ronaldo Chicken Project — Claude Code Instructions

## Project Structure

This repo contains two separate games:

| Game | File | Release Notes |
|------|------|---------------|
| Ronaldo Chicken | `ronaldo_chicken.html` | `RELEASE_NOTES.md` |
| Chicken Farm | `chicken_farm.html` | `RELEASE_NOTES_CHICKEN_FARM.md` |

## Release Notes Protocol

**MANDATORY** on every code change: update the **correct** release notes file for the game you modified.

- Changes to `ronaldo_chicken.html` → update `RELEASE_NOTES.md`
- Changes to `chicken_farm.html` → update `RELEASE_NOTES_CHICKEN_FARM.md`

Each update must include: version bump (patch/minor/major), date, summary, and changes. Update the Version History table at the top.

### Current Versions
- **Ronaldo Chicken:** v6.0.1 (2026-03-20)
- **Chicken Farm:** v0.1.0 (2026-03-17)

## Git Protocol

Commit messages should reference which game was changed, e.g.:
- `[ronaldo-chicken] v5.2.0: Add power-ups system`
- `[chicken-farm] v0.2.0: Add egg selling mechanic`

## Code Change Annotations

**MANDATORY** on every code change: add inline comment with date-time and why.
```html
<!-- [2026-03-17 14:00] Added egg hatching timer — business simulation core loop -->
```

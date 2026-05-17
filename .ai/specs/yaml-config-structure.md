---

# YAML Config Folder Structure

## What
Define the directory layout teams use to organize their Kafka resource YAML files. A consistent folder structure lets the translator discover and process configs predictably, supports multi-environment setups, and enforces ownership boundaries between teams.

## Constraints

**Do:**
- Organise configs by team, then by environment
- Keep one resource type per file (topics, acls, schemas, users)
- Use a fixed, well-known root directory for all team configs

**Don't:**
- Mix multiple teams in the same folder
- Allow arbitrary nesting beyond the defined depth
- Place environment-agnostic and environment-specific files at the same level

## Tasks

# Task 1 — Define the root config directory
Agree on a single root path (e.g. `configs/`) that the translator scans. Document the convention. *(translator)*

# Task 2 — Define the team-level directory
Each team owns a subdirectory named after the team (e.g. `configs/<team-name>/`). Define naming rules (lowercase, kebab-case, no spaces). *(translator)*

# Task 3 — Define the environment-level directory
Inside each team folder, one subdirectory per target environment (e.g. `configs/<team-name>/<env>/`). Define the allowed environment names. *(translator)*

# Task 4 — Define per-resource-type files
Inside each environment folder, one file per resource type: `topics.yaml`, `acls.yaml`, `schemas.yaml`, `users.yaml`. All files are optional; missing files mean no resources of that type. *(translator)*

# Task 5 — Implement directory discovery in the translator
Add a traversal step in the translator that walks `configs/<team>/<env>/` and loads whichever resource files are present, skipping unrecognised files with a warning. *(translator)*

---

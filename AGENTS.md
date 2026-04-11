# Repository Guide For Agents

This repository is course material for the 4-day Paris 2026 doctoral training on LCA with `brightway`, `premise`, `edges`, and optional `trails`.
Most work here is content maintenance, not application development.

## What Lives Here

- `README.MD`: course overview, learning outcomes, repository map.
- `INSTRUCTIONS.MD`: pre-arrival setup steps for participants.
- `SCHEDULE.MD`: day-by-day agenda mapped to notebooks and handouts.
- `READING_MATERIAL.md`: pre-course reading list.
- `envs/`: conda environments. The main teaching environment is `lca-course`.
- `tutorials/00_SETUP/`: pre-course setup notebook.
- `tutorials/DAY 1 - Brightway Foundations/`: Brightway basics, BAFU import, and first LCA work.
- `tutorials/DAY 2 - Brightway and Activity Browser Part I/`: `ecoinvent` import and the first Activity Browser block.
- `tutorials/DAY 3 - Premise and Activity Browser Part II/`: `premise`, scenario databases, and the second Activity Browser block.
- `tutorials/DAY 4 - Edges and Trails/`: compressed `edges` sequence plus optional `trails`.
- `tutorials/OPTIONAL/`: advanced or after-course reference notebooks.
- `data/`: bundled course data, including the BAFU workbook and LCIA Excel files.

## Course Flow

Participants are expected to:

1. Read `INSTRUCTIONS.MD`.
2. Build the `lca-course` conda environment from `envs/`.
3. Run `tutorials/00_SETUP/00 - Setup and First Checks.ipynb`.
4. Work through Day 1, Day 2, Day 3, then Day 4 in schedule order.

The schedule, notebook names, and tutorial README files should stay aligned.

## Notebook Editing Guidance

- Preserve the current teaching pattern when possible:
  title, learning goals, concept/workflow, exercise, then a minimal answer/template cell.
- Keep notebooks free of stored outputs unless the user explicitly asks for committed outputs.
- Prefer small, surgical notebook edits. Do not rewrite notebook metadata unless necessary.
- If notebook files are renamed, update links in `README.MD`, `SCHEDULE.MD`, and the relevant day-level `README.MD`.
- Day 2 through Day 4 mix concept text with lightweight scaffold exercises; keep that distinction clear if expanding them.
- When notebooks refer to local assets, prefer path handling that works both from the repository root and from the notebook folder.

## Data And Assets

- Day 1 uses the bundled file `data/lci-bafu.xlsx`.
- The BAFU website link is for reference and terms of use; participants do not download it during the course.
- `ecoinvent 3.12 cutoff` is not included in this repository; participants import it locally with their own credentials.
- Day 3 notebooks embed the course `premise` IAM key and may also honor `IAM_FILES_KEY` if it is set locally.
- Exercise assets for later days live under each day's `assets/` folder and are safe to reference in notebooks.

## Environment Files

- `envs/lca_course_osxARM.yaml` and `envs/lca_course_win64.yaml` define the main course environment.
- If changing core package guidance, keep top-level setup instructions consistent with the relevant environment file.
- Linux support is not part of the current participant-facing setup unless explicitly requested.

## Practical Cautions

- This repo may contain local-only files such as `.DS_Store`, `.idea/`, `COURSE_ADAPTATION_QUESTIONS.md`, and this `AGENTS.md`.
- Treat the repository as teaching material first: clarity, reproducibility, and stable notebook links matter more than clever refactors.

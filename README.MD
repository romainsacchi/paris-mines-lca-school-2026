# Doctoral Training: LCA with Brightway2.5, Premise and Edges (Paris, May 4-7, 2026)

![Mines Paris - PSL logo](https://www.minesparis.psl.eu/wp-content/uploads/2024/02/Logo-Mines-Paris-PSL-Bloc-Marque-Bleu-VF.png)

## Course Overview

This repository contains the teaching material for a 4-day in-person doctoral training held in Paris from May 4 to May 7, 2026 for doctoral students and researchers from the Laboratoire Recherche Environnement, Mines Paris - PSL.

The course combines:
- `brightway` 2.5 foundations
- `Activity Browser` in two guided modules
- `premise` for prospective LCA database generation
- `edges` for regionalised LCIA
- optional `trails` material for dynamic LCA if group progress allows

The format mixes short lectures, notebook work, and guided GUI handouts.

## Quick Links

- [INSTRUCTIONS.MD](INSTRUCTIONS.MD): pre-arrival setup and installation steps
- [SCHEDULE.MD](SCHEDULE.MD): day-by-day agenda with notebook and handout mapping
- [READING_MATERIAL.md](READING_MATERIAL.md): recommended pre-course reading
- [tutorials/README.MD](tutorials/README.MD): tutorial index

## Learning Outcomes

By the end of the course, participants should be able to:
- explain `brightway`'s architecture and matrix-based computation flow
- import and inspect foreground and background LCI data in Python
- run LCA, contribution analysis, and uncertainty analysis in `brightway`
- import `ecoinvent 3.12 cutoff` with the `bw2io` helper workflow
- generate prospective databases with `premise` from REMIND-EU scenarios
- compare scenarios, years, and technologies in `brightway` and `Activity Browser`
- run compact regionalised LCIA workflows with `edges`
- interpret inventory flow assessment and supply-risk style outputs
- understand how optional `trails` workflows connect to a `premise` datapackage

## Audience And Prerequisites

- doctoral students and researchers with a solid understanding of LCA concepts
- basic Python and Jupyter familiarity
- no prior `brightway` experience required

If you are rusty with Python, spend a few hours on a lightweight refresher before the course:
- https://programming-25.mooc.fi/part-1/1-getting-started

For this course, the `Introduction to Programming` section is sufficient.

## Databases And Licensing

The course uses two database tracks:

- `data/lci-bafu.xlsx`: bundled open BAFU workbook used for the Day 1 `brightway` module and the Day 4 `edges` examples
- `ecoinvent 3.12 cutoff`: required for the Day 2 `Activity Browser`, Day 3 `premise`, and optional Day 4 `trails` workflows

Important constraints:
- `ecoinvent` is not included in this repository.
- Participants should bring valid `ecoinvent` credentials for the helper import workflow.
- Course `premise` IAM decryption key: `tUePmX_S5B8ieZkkM7WUU2CnO8SmShwmAeWK9x2rTFo=`

Create a repo-root `.env` file, or start from `.env.example`, with:

```bash
IAM_FILES_KEY=tUePmX_S5B8ieZkkM7WUU2CnO8SmShwmAeWK9x2rTFo=
ECOINVENT_USERNAME=<your ecoinvent username>
ECOINVENT_PASSWORD=<your ecoinvent password>
```

The Day 2, Day 3, and optional Day 4 notebooks load this file automatically with `python-dotenv`.

BAFU reference page:
- https://nexus.openlca.org/database/BAFU

## Repository Structure

- `data/`: bundled course data, including the BAFU workbook
- [tutorials/00_SETUP/](tutorials/00_SETUP/README.MD): pre-course setup and first checks
- [tutorials/DAY 1 - Brightway Foundations/](tutorials/DAY%201%20-%20Brightway%20Foundations/README.MD): Python/Jupyter refresher plus core `brightway` work
- [tutorials/DAY 2 - Brightway and Activity Browser Part I/](tutorials/DAY%202%20-%20Brightway%20and%20Activity%20Browser%20Part%20I/README.MD): `ecoinvent` import and the first `Activity Browser` block
- [tutorials/DAY 3 - Premise and Activity Browser Part II/](tutorials/DAY%203%20-%20Premise%20and%20Activity%20Browser%20Part%20II/README.MD): `premise` and scenario comparison
- [tutorials/DAY 4 - Edges and Trails/](tutorials/DAY%204%20-%20Edges%20and%20Trails/README.MD): compressed `edges` sequence plus optional `trails`
- [tutorials/OPTIONAL/](tutorials/OPTIONAL/README.MD): advanced or reference notebooks not in the core path
- [READING_MATERIAL.md](READING_MATERIAL.md): suggested background reading

## Recommended Workflow

Before the course:

1. Follow [INSTRUCTIONS.MD](INSTRUCTIONS.MD).
2. Create and activate the `lca-course` conda environment.
3. Run [tutorials/00_SETUP/00 - Setup and First Checks.ipynb](tutorials/00_SETUP/00%20-%20Setup%20and%20First%20Checks.ipynb).

During the course:

4. Work through Day 1, Day 2, Day 3, then Day 4 in the order shown in [SCHEDULE.MD](SCHEDULE.MD).
5. Keep using the same `lca-course` environment and the same Brightway project, `paris-lca-course-2026`.

## Software

Core environment files are in `envs/`:
- `lca_course_osxARM.yaml` for macOS Apple Silicon
- `lca_course_win64.yaml` for Windows

Both install the same shared `lca-course` environment used for notebooks and `Activity Browser`.

## Teaching Staff

- [Romain Sacchi](mailto:romain.sacchi@psi.ch), main instructor for `brightway`, `premise`, `edges`, and `trails`
- [Bernhard Steubing](mailto:b.r.p.steubing@cml.leidenuniv.nl), instructor for the `Activity Browser` modules
- Format: in-person lectures and hands-on workshops
- Location: Mines Paris - PSL, Paris, France

## License

Unless otherwise specified, material in this repository is licensed under BSD 3-Clause. See [LICENSE.md](LICENSE.md).

# DAY 3 - Premise and Activity Browser Part II

Run these materials after completing Day 2 in the same `lca-course` environment and Brightway project.

Before starting Day 3, make sure that:
- `paris-lca-course-2026` contains `ecoinvent-3.12-cutoff`
- the repo-root `.env` file is present, ideally with `IAM_FILES_KEY`, `ECOINVENT_USERNAME`, and `ECOINVENT_PASSWORD`
- you are ready to generate and compare REMIND-EU scenario databases

Core material:

1. `D3-01 Premise readiness checks and scenario framing.ipynb`
2. `paris_premise_intro_06_05_2026.pdf`
3. `D3-02 Generating prospective databases with premise.ipynb`
4. `D3-03 Inspecting and comparing premise outputs in Brightway.ipynb`
5. `AB-02 Activity Browser Part II handout.md`

The Day 3 sequence starts with a one-hour introduction lecture, then moves into database generation in Brightway and datapackage export for optional `trails` work.
The Premise notebooks load the repo-root `.env` file automatically with `python-dotenv`, and still fall back to the embedded course key if `IAM_FILES_KEY` is absent.
The Activity Browser handout then focuses on scenario, year, and technology comparisons in the GUI.

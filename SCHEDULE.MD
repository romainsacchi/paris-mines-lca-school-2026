# Course Schedule

The schedule below maps each teaching block to specific notebooks or handouts.
Break durations can still be adjusted during the course.

## PRIOR TO ARRIVAL

Complete:
- [INSTRUCTIONS.MD](INSTRUCTIONS.MD)
- [tutorials/00_SETUP/00 - Setup and First Checks.ipynb](tutorials/00_SETUP/00%20-%20Setup%20and%20First%20Checks.ipynb)
- [READING_MATERIAL.md](READING_MATERIAL.md)

## How to open the notebooks

```bash
conda activate lca-course
jupyter lab
```

## DAY 1 (Monday, May 4, 2026) - Brightway Foundations

Instructor: Romain Sacchi

### 09:00 - 09:30
Welcome, setup check, course roadmap, Python/Jupyter refresher
- [D1-01 Python and Jupyter minimum refresher](tutorials/DAY%201%20-%20Brightway%20Foundations/D1-01%20Python%20and%20Jupyter%20minimum%20refresher.ipynb)

### 09:30 - 10:30
`brightway` architecture and core data model
- [D1-02 Brightway architecture and data model](tutorials/DAY%201%20-%20Brightway%20Foundations/D1-02%20Brightway%20architecture%20and%20data%20model.ipynb)

### 10:30 - 11:00
Coffee break

### 11:00 - 13:00
Manual matrix LCA, first LCA, and BAFU import
- [D1-03 Manual LCA with NumPy matrices - Heijungs and Suh 2002 vs Brightway](tutorials/DAY%201%20-%20Brightway%20Foundations/D1-03%20Manual%20LCA%20with%20NumPy%20matrices%20-%20Heijungs%20and%20Suh%202002%20vs%20Brightway.ipynb)
- [D1-04 First LCA from demand to score in Brightway](tutorials/DAY%201%20-%20Brightway%20Foundations/D1-04%20First%20LCA%20from%20demand%20to%20score%20in%20Brightway.ipynb)

### 13:00 - 15:00
Lunch break

### 15:00 - 16:30
Uncertainty and Monte Carlo
- [D1-05 Uncertainty and Monte Carlo basics](tutorials/DAY%201%20-%20Brightway%20Foundations/D1-05%20Uncertainty%20and%20Monte%20Carlo%20basics.ipynb)

### 16:30 - 17:00
Coffee break

### 17:00 - 19:00
Data QA, linking workflow, and contribution analysis
- [D1-06 Data quality checks and linking workflow](tutorials/DAY%201%20-%20Brightway%20Foundations/D1-06%20Data%20quality%20checks%20and%20linking%20workflow.ipynb)
- [D1-07 Contribution analysis and result visualization](tutorials/DAY%201%20-%20Brightway%20Foundations/D1-07%20Contribution%20analysis%20and%20result%20visualization.ipynb)

## DAY 2 (Tuesday, May 5, 2026) - Brightway to ecoinvent and Activity Browser Part I

Morning instructor: Romain Sacchi
Afternoon instructor: Bernhard Steubing

### 09:00 - 10:30
Return to the shared project, import `ecoinvent 3.12 cutoff`, and check the database state
- [D2-01 ecoinvent import and Brightway recap](tutorials/DAY%202%20-%20Brightway%20and%20Activity%20Browser%20Part%20I/D2-01%20ecoinvent%20import%20and%20Brightway%20recap.ipynb)

### 10:30 - 11:00
Coffee break

### 11:00 - 13:00
Inspect imported activities, rerun one compact LCA, and prepare the project for the GUI module
- [D2-01 ecoinvent import and Brightway recap](tutorials/DAY%202%20-%20Brightway%20and%20Activity%20Browser%20Part%20I/D2-01%20ecoinvent%20import%20and%20Brightway%20recap.ipynb)

### 13:00 - 15:00
Lunch break

### 15:00 - 16:30
Activity Browser Part I: parameterisation, Monte Carlo, and GSA
- [AB-01 Activity Browser Part I handout](tutorials/DAY%202%20-%20Brightway%20and%20Activity%20Browser%20Part%20I/AB-01%20Activity%20Browser%20Part%20I%20handout.md)

### 16:30 - 17:00
Coffee break

### 17:00 - 19:00
Activity Browser Part I continued
- [AB-01 Activity Browser Part I handout](tutorials/DAY%202%20-%20Brightway%20and%20Activity%20Browser%20Part%20I/AB-01%20Activity%20Browser%20Part%20I%20handout.md)

## DAY 3 (Wednesday, May 6, 2026) - Premise and Activity Browser Part II

Morning instructor: Romain Sacchi
Afternoon instructor: Bernhard Steubing

### 09:00 - 10:00
Start generating prospective databases with `premise`
- [D3-01 Generating prospective databases with premise](tutorials/DAY%203%20-%20Premise%20and%20Activity%20Browser%20Part%20II/D3-01%20Generating%20prospective%20databases%20with%20premise.ipynb)

### 10:00 - 11:00
Premise introduction lecture: IAMs, scenarios, and prospective LCA workflow
- [paris_premise_intro_06_05_2026.pdf](tutorials/DAY%203%20-%20Premise%20and%20Activity%20Browser%20Part%20II/paris_premise_intro_06_05_2026.pdf)

### 11:00 - 13:00
Continue `premise` generation, checks, and datapackage export
- [D3-01 Generating prospective databases with premise](tutorials/DAY%203%20-%20Premise%20and%20Activity%20Browser%20Part%20II/D3-01%20Generating%20prospective%20databases%20with%20premise.ipynb)

### 13:00 - 15:00
Lunch break

### 15:00 - 16:30
Inspect and compare generated outputs in Brightway
- [D3-02 Inspecting and comparing premise outputs in Brightway](tutorials/DAY%203%20-%20Premise%20and%20Activity%20Browser%20Part%20II/D3-02%20Inspecting%20and%20comparing%20premise%20outputs%20in%20Brightway.ipynb)

### 16:30 - 17:00
Coffee break

### 17:00 - 19:00
Activity Browser Part II: compare prospective scenarios
- [AB-02 Activity Browser Part II handout](tutorials/DAY%203%20-%20Premise%20and%20Activity%20Browser%20Part%20II/AB-02%20Activity%20Browser%20Part%20II%20handout.md)

## DAY 4 (Thursday, May 7, 2026) - Edges and Trails

Instructor: Romain Sacchi

### 09:00 - 10:00
Exchange-based characterization and `edges` fundamentals
- [D4-01 Edges fundamentals and exchange-based characterization](tutorials/DAY%204%20-%20Edges%20and%20Trails/D4-01%20Edges%20fundamentals%20and%20exchange-based%20characterization.ipynb)

### 10:00 - 10:30
Introduction to the `edges` workflow and API
- [D4-02 Introduction to edges workflow and API](tutorials/DAY%204%20-%20Edges%20and%20Trails/D4-02%20Introduction%20to%20edges%20workflow%20and%20API.ipynb)

### 10:30 - 11:00
Coffee break

### 11:00 - 13:00
AWARE and biodiversity examples with regionalised methods
- [D4-03 AWARE and biodiversity with regionalised methods](tutorials/DAY%204%20-%20Edges%20and%20Trails/D4-03%20AWARE%20and%20biodiversity%20with%20regionalised%20methods.ipynb)

### 13:00 - 15:00
Lunch break

### 15:00 - 16:00
Inventory flow assessment I
- [D4-04 Inventory flow assessment I - tracing intermediates](tutorials/DAY%204%20-%20Edges%20and%20Trails/D4-04%20Inventory%20flow%20assessment%20I%20-%20tracing%20intermediates.ipynb)

### 16:00 - 16:15
Coffee break

### 16:15 - 17:15
Inventory flow assessment II
- [D4-05 Inventory flow assessment II - criticality factors](tutorials/DAY%204%20-%20Edges%20and%20Trails/D4-05%20Inventory%20flow%20assessment%20II%20-%20criticality%20factors.ipynb)

### 17:15 - 19:00
Optional `trails` reserve block, if group progress allows
- [D4-06 Optional Trails - simple numerical example](tutorials/DAY%204%20-%20Edges%20and%20Trails/D4-06%20Optional%20Trails%20-%20simple%20numerical%20example.ipynb)
- [D4-07 Optional Trails - generate a data package from premise outputs](tutorials/DAY%204%20-%20Edges%20and%20Trails/D4-07%20Optional%20Trails%20-%20generate%20a%20data%20package%20from%20premise%20outputs.ipynb)
- [D4-08 Optional Trails - premise and imported LCI example](tutorials/DAY%204%20-%20Edges%20and%20Trails/D4-08%20Optional%20Trails%20-%20premise%20and%20imported%20LCI%20example.ipynb)

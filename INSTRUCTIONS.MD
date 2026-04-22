# INSTRUCTIONS BEFORE ARRIVAL

Please complete these steps before the course starts.
The goal is to spend Day 1 learning, not debugging installations.

If you get stuck, contact:
`romain.sacchi@psi.ch`

## Minimum hardware

- Minimum: `8 GB` RAM
- Preferred: `16 GB` RAM

## Before you start

- A stable internet connection is needed to install Git, Miniforge, and the packages in the `lca-course` environment.
- You need valid `ecoinvent` credentials for the Day 2 import and the Day 3 `premise` work.
- The BAFU workbook used in Day 1 is already bundled at `data/lci-bafu.xlsx`.
- The course `premise` IAM decryption key is `tUePmX_S5B8ieZkkM7WUU2CnO8SmShwmAeWK9x2rTFo=`.
- You will create a repo-root `.env` file later with `IAM_FILES_KEY`, `ECOINVENT_USERNAME`, and `ECOINVENT_PASSWORD`.

## What these tools are for

- `Git`: downloads and updates this course repository.
- `Miniforge` / `conda`: installs Python packages in an isolated environment.
- `Jupyter Lab`: runs the tutorial notebooks.
- `brightway`: is the main Python framework used in the course for LCA modeling and calculation.
- `Activity Browser`: is a graphical user interface for `brightway`, installed inside the same course environment.
- `premise`: generates prospective LCI databases from IAM scenarios.
- `edges`: runs exchange-based and regionalized LCIA workflows.
- `trails`: supports the optional dynamic and temporal LCA examples.

## If you are new to Python

If you are completely new to Python, we recommend spending a few hours on a beginner tutorial before the course.
We suggest the University of Helsinki's online tutorial, which requires no installation:

- https://programming-25.mooc.fi/part-1/1-getting-started

For this course, the `Introduction to Programming` section is sufficient.
You do not need to complete the `Advanced Course in Programming` section.

## 1) Install Git and Miniforge

Install:
- Git: https://git-scm.com/downloads
- Miniforge: https://github.com/conda-forge/miniforge/releases/latest

Mac example for Git:

```bash
brew install git
```

### Miniforge installation

Mac users:
- Open `Terminal`
- Download and run the official installer for your Mac architecture:

```bash
curl -L -O "https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-MacOSX-$(uname -m).sh"
bash Miniforge3-MacOSX-$(uname -m).sh
```

- Accept the prompt to initialize `conda` for your shell.

Windows users:
- Download `Miniforge3-Windows-x86_64.exe`
- Run the installer and keep the Start Menu shortcuts enabled.
- After installation, open the **Miniforge Prompt** from the Start Menu.
- If possible, install Miniforge in a path without spaces or special characters.

Check that both tools are available:

```bash
git --version
conda --version
```

## 2) Clone this repository

You can use GitHub Desktop or the terminal. Terminal example:

```bash
mkdir GitHub
cd GitHub
git clone https://github.com/romainsacchi/paris-mines-lca-school-2026.git
cd paris-mines-lca-school-2026
```

## 3) Create the course environment (`lca-course`)

From the repository root:

```bash
cd envs
```

Choose one command:

- macOS Apple Silicon:

```bash
conda env create -f lca_course_osxARM.yaml
```

- Windows:

```bash
conda env create -f lca_course_win64.yaml
```

Then verify:

```bash
conda env list
```

You should see `lca-course` in the list.

## 4) Install the Activity Browser

Please install the beta version of the AB, following the official installation guide here:
https://lca-activitybrowser.github.io/activity-browser/getting-started/installation.html

This will create a _separate_ environment called `ab_beta`. For this course we recommend the `conda` based installation so both environments are managed via conda. 

Once installed, you can activate the AB by typing 
```bash 
conda activate ab_beta
```

Then start the AB 
```bash 
activity-browser
``` 

Close the AB and type 
```bash 
conda deactivate
``` 
to deactivate the environment. Alternatively, you can keep the AB open and open another terminal to continue.
    
## 5) Activate `lca-course`

Activate in the same shell:

```bash
conda activate lca-course
```

## 6) Create a repo-root `.env` file

If you are still in `envs/`, go back to the repository root first.

Create a file named `.env` in the repository root with:

```bash
IAM_FILES_KEY=tUePmX_S5B8ieZkkM7WUU2CnO8SmShwmAeWK9x2rTFo=
ECOINVENT_USERNAME=<your ecoinvent username>
ECOINVENT_PASSWORD=<your ecoinvent password>
```

You can also start from `.env.example`.

The Day 2, Day 3, and optional Day 4 notebooks load this file automatically with `python-dotenv`.
The `.env` file is ignored by Git and should stay local.

## 7) Run quick import checks

Still in the activated `lca-course` environment:

```bash
python --version
python -c "import bw2data, bw2calc, bw2io, premise; print('Core imports: OK')"
```

### Apple Silicon note about the sparse solver warning

On Apple Silicon, `bw2calc` may print a warning about missing `scikit-umfpack`.
If that happens after creating the environment, run:

```bash
conda activate lca-course
conda install "setuptools<81"
```

Then verify:

```bash
python -c "import scikits.umfpack; print('UMFPACK import: OK')"
```

If the environment is still inconsistent, recreate it from the YAML file.

## 8) Confirm the bundled BAFU workbook is present

From the repository root:

```bash
ls data/lci-bafu.xlsx
```

If the file exists, you do not need any separate BAFU download before the course.

## 9) Start Jupyter Lab and run the setup notebook

From the repository root:

```bash
conda activate lca-course
jupyter lab
```

Then open:
- `tutorials/00_SETUP/00 - Setup and First Checks.ipynb`

## 10) Before the course starts

Please complete:
- [READING_MATERIAL.md](READING_MATERIAL.md)
- [tutorials/00_SETUP/00 - Setup and First Checks.ipynb](tutorials/00_SETUP/00%20-%20Setup%20and%20First%20Checks.ipynb)

Keep the same `lca-course` environment for the full course.
Keep the same Brightway project name used in the notebooks: `paris-lca-course-2026`.

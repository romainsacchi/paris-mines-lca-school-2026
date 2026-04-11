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

## What these tools are for

- `Git`: downloads and updates this course repository.
- `Miniforge` / `conda`: installs Python packages in an isolated environment.
- `Jupyter Lab`: runs the tutorial notebooks.
- `Activity Browser`: is installed inside the same course environment.

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
git clone https://github.com/romainsacchi/paris-mines-lca-school-2026.git paris-mines-lca-course-2026
cd paris-mines-lca-course-2026
```

The clone command above keeps the GitHub repository slug while giving the local folder the course-friendly name `paris-mines-lca-course-2026`.

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

## 4) Activate `lca-course`

Activate in the same shell:

```bash
conda activate lca-course
```

## 5) Configure the `premise` IAM key locally

The Day 3 `premise` notebooks expect an environment variable named `IAM_FILES_KEY`.
The notebooks now also include the course key directly, but setting it once in your environment keeps the workflow cleaner.

Recommended approach:

```bash
conda activate lca-course
conda env config vars set IAM_FILES_KEY="tUePmX_S5B8ieZkkM7WUU2CnO8SmShwmAeWK9x2rTFo="
conda deactivate
conda activate lca-course
```

Optional convenience variables for the `ecoinvent` helper import:

```bash
conda env config vars set EI_USERNAME="<your ecoinvent username>"
```

You can enter the `ecoinvent` password interactively in the notebook, or store it locally in the same way if you prefer.

## 6) Run quick import checks

Still in the activated `lca-course` environment:

```bash
python --version
python -c "import bw2data, bw2calc, bw2io, premise; print('Core imports: OK')"
```

If you want to check the GUI package too:

```bash
python -c "import activity_browser; print('Activity Browser import: OK')"
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

## 7) Confirm the bundled BAFU workbook is present

From the repository root:

```bash
ls data/lci-bafu.xlsx
```

If the file exists, you do not need any separate BAFU download before the course.

## 8) Start Jupyter Lab and run the setup notebook

From the repository root:

```bash
conda activate lca-course
jupyter lab
```

Then open:
- `tutorials/00_SETUP/00 - Setup and First Checks.ipynb`

## 9) Before the course starts

Please complete:
- [READING_MATERIAL.md](READING_MATERIAL.md)
- [tutorials/00_SETUP/00 - Setup and First Checks.ipynb](tutorials/00_SETUP/00%20-%20Setup%20and%20First%20Checks.ipynb)

Keep the same `lca-course` environment for the full course.
Keep the same Brightway project name used in the notebooks: `paris-lca-course-2026`.

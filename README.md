# ENGG2112 crop yield analysis

This project explores whether rainfall, agricultural inputs, temperature and humidity help predict crop yield across three Indian regions. The notebook includes data checks, exploratory charts, wheat and moong case studies, and comparisons against simple historical-yield baselines.

## Project files

- `exploration.ipynb`: the analysis, explanations and saved results.
- `requirements.txt`: the Python packages needed to run the notebook.
- `data/raw/BronzeLayer_data.csv`: the crop dataset.
- `data/external/nasa_power/t2m_rh2m_1996_2021/`: cached NASA POWER weather responses, monthly weather and sampling coordinates.

## Run locally in VS Code

Install Python 3.11 or 3.13 and the Python and Jupyter extensions for VS Code. Clone this repository, or download and extract its ZIP, then open the project folder in VS Code.

Open a terminal in that folder and create an environment with the dependencies:

### Windows (PowerShell)

```powershell
python -m venv .venv
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
```

### macOS or Linux

```bash
python3 -m venv .venv
.venv/bin/python -m pip install -r requirements.txt
```

Open `exploration.ipynb`, choose **Select Kernel**, select the Python interpreter inside `.venv`, and choose **Run All**. Use the project folder as the working directory so the relative data paths resolve correctly. The final model comparison can take several minutes.

The original author's `engg2112` environment is not required. Each reader creates their own environment; the notebook's saved kernel name does not install or select that environment for them.

An internet connection is needed to install packages. The included weather JSON files allow the weather section to reuse cached responses; if a response is missing, the notebook requests it from NASA POWER. Keep the `data` directory alongside the notebook.

## Interpreting the results

The two crop examples show improvements in particular test periods, but the broader comparison favours the last recorded yield for each state and season over the tested complex models. The notebook explains the scoring methods, uncertainty and limitations. Its analysis uses crop records through 2014 and is exploratory; observed annual inputs may not be available at the time a real forecast is needed.

The analysis was run successfully in the author's local environment. Installation on every operating system has not been tested. The crop dataset's original citation, measurement units and reuse terms still need to be documented; including the data here does not establish its licence.

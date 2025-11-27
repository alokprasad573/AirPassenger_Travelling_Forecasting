AirPassengers Forecasting with Prophet

Overview
This repository contains a simple time series forecasting workflow using Facebook Prophet (now Prophet) on the classic AirPassengers dataset. The Jupyter notebook loads monthly passenger counts, fits a Prophet model, generates a 24-month forecast, visualizes components and forecast bands, evaluates error (RMSE), and exports a CSV of actuals and predictions.

Repository Contents
- AirPassengers.csv — Source dataset (Month, Passengers) used by the notebook.
- FlightUasageForecasting.ipynb — Main Jupyter notebook that performs forecasting and visualization.
- flight_usage_forecast.csv — Forecast results exported by the notebook (created after running the notebook).
- README.md — This documentation.

Tech Stack and Entry Point
- Language: Python
- Primary libraries/frameworks:
  - prophet (Prophet / formerly fbprophet)
  - pandas
  - numpy
  - matplotlib
  - scikit-learn (used for RMSE metric)
- Environment/IDE: Jupyter Notebook or JupyterLab
- Entry point: FlightUasageForecasting.ipynb (open and run all cells)

Requirements
- Python: a recent Python 3 version. TODO: Pin exact version after verifying (e.g., 3.10/3.11).
- OS: Any supported by Python and Prophet (Windows/Linux/macOS). Note: Prophet may require compiler/build tools.
- Packages:
  - prophet
  - pandas
  - numpy
  - matplotlib
  - scikit-learn

Setup
1) Create and activate a virtual environment (recommended)
- Using venv (cross-platform):
  - Windows PowerShell:
    - python -m venv .venv
    - .venv\\Scripts\\Activate.ps1
  - macOS/Linux:
    - python3 -m venv .venv
    - source .venv/bin/activate

2) Install dependencies
- If you have a requirements.txt (not included yet):
  - pip install -r requirements.txt
- Or install packages individually:
  - pip install prophet pandas numpy matplotlib scikit-learn

3) (Optional) Jupyter tools
- pip install jupyterlab or pip install notebook

Running the Project
Option A: JupyterLab
- jupyter lab
- Open FlightUasageForecasting.ipynb and run all cells (Kernel → Restart Kernel and Run All Cells).

Option B: Classic Jupyter Notebook
- jupyter notebook
- Open FlightUasageForecasting.ipynb and run all cells (Kernel → Restart & Run All).

Data and Outputs
- Input data: AirPassengers.csv must be in the same directory as the notebook. The notebook renames columns to Prophet’s expected schema (Month → ds, Passengers → y) and applies a log transform on y for modeling.
- Forecast horizon: 24 months (periods=24) at monthly end frequency (freq='ME').
- Plots: The notebook visualizes forecast components and the actual vs. predicted series with 95% intervals.
- Metrics: RMSE between actual and predicted values is computed.
- Output file: flight_usage_forecast.csv with columns [Month, Actual_Passenger_Data, Predicted_Passenger_Data, Lower_Limit, Upper_Limit]. This is generated when the notebook completes.

Scripts and Commands
There are no standalone CLI scripts. All logic is contained within FlightUasageForecasting.ipynb. Useful commands:
- Start JupyterLab: jupyter lab
- Start Notebook: jupyter notebook

Environment Variables
- None required for the current workflow.
- Document any future configurable parameters as environment variables (e.g., forecast horizon, paths) if the notebook is parameterized later.

Tests
- There are currently no automated tests in this repository.
- Add lightweight checks, e.g.:
  - Verify AirPassengers.csv schema
  - Unit tests for any future refactored functions (if notebook code is modularized into .py files)

Project Structure
AirPassenger/
- AirPassengers.csv
- FlightUasageForecasting.ipynb
- flight_usage_forecast.csv (generated after running the notebook)
- README.md

Notes
- The notebook filename contains a small typo (Uasage vs Usage). Functionality is unaffected. TODO: Consider renaming in a future change and updating references accordingly.
- Prophet package installation may vary by platform. If you encounter installation issues, ensure build tools are installed or try a different Python version compatible with Prophet.


Acknowledgments
- AirPassengers dataset is a well-known public time series used in forecasting examples.
- Prophet library: https://github.com/facebook/prophet


---------------------------
INSTRUCTION ON RUNNING CODE
---------------------------

1. Primarily, make sure to run the requirements.txt file in a fresh environment:
    pip install -r requirements.txt
2. Next, load data.xlsx in the same working folder as the IPYNB file.
2. After that, simply run each cell sequentially.
3. Note that running all the cells will also save the 4 CSV deliverables as well.

---------------------------
DESCRIPTION OF DELIVERABLES
---------------------------

- CSV Files
    - anomalous_periods.csv shows at what time the anomaly occurs.
    - clusters_summary.csv provides summary statistics for each of the 6 variables across all three state clusters.
    - forecasts.csv contains last 12 time points with actual values and corresponding persistence and ARIMA forecast predictions.
    - shutdown_periods shows all the starting date, ending date, and duration of sensor machine shutdowns.

- Code
    - Runnable IPYNB file.

- plots
    - Each plot is names in a way where the numbering is based on code running sequence, followed a by small title.
    - Example: "12. data-2020-year-slice.png" means that it is the 12th plot that you will get when you run the notebook and it is the plot that shows the data for the year 2020 for all the 6 variables.
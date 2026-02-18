The application is organised into seven tabs. Follow the workflow from left to right.
The source can be run on either a Jupyter notebook or any Python-readable framework.
This enhanced GUI application can handle temporal normalisation  of the River Benue water quality dataset, resulting in more accurate and reliable forecasts of its water quality indices based on six different aggregation functions.
The water plant manager can use this tool to predict future monthly water quality indices per season with confidence in the underlying normalisation and modelling processes.
Data Loading
Browse for your water quality data file (Excel or CSV).

Browse for the guidelines file (CSV) containing threshold values.

Click Preprocess Data to convert numeric columns, handle missing values, and normalise temporal features (year, month, season).

A preview of the raw data is shown in the text area.
Feature Selection
Adjust Boruta parameters (max iterations, tree depth, include tentative features).

Click Run Feature Selection.

The algorithm identifies the most important water quality variables; results appear in a table and as a horizontal bar plot.
Sub‑index Calculation
Click Calculate Sub‑indices to compute sub‑index values for the selected parameters according to the guidelines.

A sample table and a seasonal comparison plot are generated (full implementation requires the equations from Table 1).
Weight Calculation
Click Calculate Weights to obtain ROC‑based weights for dry and wet seasons.

The weights are displayed in a table and as a bar chart.
WQI Calculation
Choose one of the six aggregation methods from the dropdown.

Click Calculate WQI to compute the WQI values and assign quality classes (Excellent, Good, Medium, Poor, Very Poor).

A monthly trend plot visualises the results.
Model Training
Select the WQI method and model type (regression or classification).

Click Train Models to train RF, ETR, and XGBoost models.

Performance metrics are shown in a table, and a comparison plot is generated.
Prediction
Enter the water quality parameter values, month, season, and year.

Click Predict WQI to obtain the predicted WQI value and its class.

Use Predict Monthly WQI to generate forecasts for all twelve months.

Save the monthly predictions to a CSV file.
Input Data Format
Water Quality Data (Excel/CSV)
The file should contain at least the following columns:
PS (pollution status) is used as the target variable for feature selection and model training.

Additional parameters (TDS, EC, Pb, Cd, Cu, Fe) may be present but are not mandatory for the core workflow.
Guidelines File (CSV)
A CSV file with the following structure (skip the first two header rows):
The application automatically cleans and parses this file.

Dependencies
Python ≥ 3.7

pandas

numpy

matplotlib

seaborn

scikit-learn

xgboost

boruta‑python

tkinter (included with standard Python distributions)

Troubleshooting
Missing dependencies: Install all required packages using the command above.

File not loading: Ensure the file is in the correct format and encoding (UTF‑8). Use the provided sample files for testing.

Boruta takes a long time: Reduce max_iter or max_depth in the Feature Selection tab.

Prediction values are random: The current version includes placeholder logic for demonstration. Replace the placeholder code in predict_wqi and predict_monthly_wqi with your trained model.

Contributing
Contributions are welcome! Please fork the repository and submit a pull request with your improvements.

License
This project is licensed under the MIT License – see the LICENSE file for details.

Contact
For questions or suggestions, please contact [your email] or open an issue on GitHub.

Acknowledgements
This application was developed for the River Benue water treatment plant (GMWTP) as part of a water quality monitoring project.

Special thanks to the developers of the Boruta, scikit‑learn, and XGBoost libraries.

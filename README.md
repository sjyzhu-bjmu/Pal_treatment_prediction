# Pal_treatment_prediction

This project provides a Linux command-line toolkit for predicting six-week paliperidone treatment response (0 = poor response, 1 = response) in patients with schizophrenia using baseline metabolomic and proteomic features. The toolkit includes eight sets of models (metabolomic, proteomic, and stacking), developed with cross-site validation as described in the corresponding publication. It is distributed as a standalone binary executable for Linux and does not require a Python environment.


### 1. Input Data
- Sample input files can be found in the test_samples/ directory.


### 2. Configuration File (JSON)
```json
{
  "df_metab_test": "./your_metab_test.csv",
  "df_prot_test": "./your_prot_test.csv",
  "mode": "MP",
  "output": "./"
}
```
Mode options:
- `"M"`: Use only metabolomic models for prediction
- `"P"`: Use only proteomic models for prediction
- `"MP"`: Multi-omics integration (stacking models)


### 3. Execution
Assuming you have obtained the binary executable TRpredict (for Linux):
```bash
./TRpredict --config config.json
```
After execution, the prediction results will be saved in the output directory specified in the config.json file.


### 4. Output
- Metabolomic model predictions: `preds_M.csv`
- Proteomic model predictions: `preds_P.csv`
- Stacking model predictions: `preds_Stack.csv`

Each file contains prediction results from eight models, with column names model0 to model7.

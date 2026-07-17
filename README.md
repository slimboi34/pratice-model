# Swiss Re Variable Annuity Cashflow Projection Model
**Financial Transactions Modeler Case Study**

## Overview
This notebook builds a deterministic monthly projection model for a Variable Annuity portfolio with:
- Return of Premium GMDB (base)
- 6% Annual Roll-up GMDB rider
- 5% GLWB rider

The model runs over 40 years (480 months) and calculates fees, claims, and Net Present Value under the base case and selected shock scenarios.

## Files Included
- `model_j_notebook.ipynb` — Main Jupyter Notebook with full model + visuals
- `final_results.xlsx` — Multi-sheet Excel output with summary and monthly projections
- `SwissRe_VA_CaseStudy_Results.xlsx` — Professional formatted results
- `net_pv_comparison.png` & `pv_breakdown.png` — Supporting charts

## How to Run
1. Place all files in the same folder as the notebook.
2. Open `model_j_notebook.ipynb` in Jupyter.
3. Run all cells from top to bottom.
4. The notebook will automatically generate:
   - Summary table
   - Interactive charts (if Plotly is installed)
   - `final_results.xlsx`

## Key Results (from this run)
- **Base Net PV**: [Insert your number here]
- **Roll-up Rider Impact**: [Insert your number here]
- **GLWB Rider Impact**: [Insert your number here]
- **Equity -20% Shock**: [Insert your number here]
- **IR Shock**: [Insert your number here]

## Modelling Approach & Choices
- Deterministic cohort projection (as specified)
- Monthly conversion of rates using exact survival method: `1 - (1 - q)^(1/12)`
- Sequential decrements (deaths then lapses)
- Fee floor implemented
- Proportional GMDB Benefit Base reduction on GLWB withdrawals
- Shocks applied only to initial Account Value allocation

## Assumptions & Simplifications
- Constant fund returns (for demo)
- No mortality improvement
- No dynamic policyholder behaviour
- Partial month effects ignored
- No taxes, commissions, or hedging costs

## Part F – Additional Considerations
- Mortality improvement should be validated and stressed
- Dynamic lapse rates are important for GLWB profitability
- Exact timing of policy anniversaries and fee calculations should be clarified
- Hedging costs and capital requirements were excluded per spec but are material in practice
- Only one deterministic fund path was provided — stochastic analysis would be valuable

## Clarifying Questions I Would Ask
- Exact definition of "average Account Value for the quarter"
- Precise alignment of policy anniversaries and birthdays
- Whether GLWB withdrawals start exactly on the 10th anniversary month
- Preferred output format and level of detail for production use

## Author Notes
This submission prioritises clarity, correct implementation of product mechanics, and transparent assumptions over micro-optimisation. The model structure is designed to be easy to extend (e.g. stochastic runs, dynamic behaviour).

Prepared for Swiss Re Financial Transactions Modeler assessment — July 2026.# pratice-model

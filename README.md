MODELLING SÃO PAULO’S TRANSPORT SECTOR NET-ZERO TRANSITION: INTEGRATION OF HYDROTREATED VEGETABLE OIL (HVO) INTO THE STATE’S ENERGY MATRIX.


HVO–DIESEL BLENDING: EMISSIONS, CARBON CREDITS, AND FORECASTING

This repository contains a notebook that analyses diesel-HVO blending scenarios and compares historical emissions, avoided emissions (carbon credits), regression-based projections, and a PyTorch FNN-based BAU projection workflow. It also includes dataset augmentation, comparisons of raw versus augmented statistics, and sensitivity analysis.

ANALYSIS WORKFLOW
Historical blend emissions and carbon credits calculates emissions and avoided emissions for the blend cases defined in the notebook and produces comparison plots.
Quadratic regression — fits a separate second-degree polynomial regression model for each blend and predicts emissions for 2030, 2040, and 2050.
Dataset augmentation — rebuilds a 1,000-row augmented dataset from the raw HVO dataset using the noise and clipping procedure defined in the code.
BAU FNN projections — uses the PyTorch FNN workflow and the BAU controls, ensemble settings, and Monte Carlo sampling parameters defined in the notebook.
Sensitivity analysis — compares emissions and carbon credits over the mileage and fuel-efficiency scenarios specified in the final cell.

REPOSITORY FILES
“HVO_Diesel_Blending_PALATIA.ipynb”— organized notebook containing the original analysis/model workflow, Markdown section descriptions, Palatia typography setup, saved outputs, and plots.

“HVO_Diesel_Blending_PALATIA.py” — cell-ordered Python export for source review and version control. Run the notebook in Colab/Jupyter for the intended cell-by-cell workflow.

“DIESEL__DATA.csv”— diesel data file read by the historical emissions and sensitivity-analysis cells.

“HVO__RAW.csv” — raw HVO/blend dataset read by the augmentation, comparison, and historical/projection plotting cells.

“HVO___RAW.csv”— raw HVO/blend dataset path expected by the sensitivity-analysis cell (note the three underscores).

RUN IN GOOGLE COLAB
Open “HVO_Diesel_Blending_PALATIA.ipynb” in Google Colab.
Upload “DIESEL__DATA.csv” to /content/.

REPRODUCIBILITY
The BAU FNN cell sets Python, NumPy, and PyTorch random seeds using “SEED = 42” and configures deterministic cuDNN behaviour in its “set_seed” function. Exact reproducibility can still depend on package versions, hardware, and CUDA/cuDNN configuration. The augmentation cell uses NumPy random noise but does not explicitly set a seed immediately before augmentation in that cell; do not assume the entire notebook is deterministic solely from the BAU model seed.

ABOUT THIS CLEANUP
The code was cleaned for presentation and navigation. Markdown title and section-heading cells were added, and the original code cell source and saved outputs were retained. 

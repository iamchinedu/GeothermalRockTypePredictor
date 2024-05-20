# Geothermal Rock Type Predictor

## Project Understanding
This project aims to predict the types of rock formations—specifically Alluvium, Rhyolite, and Plutonic rocks—encountered during geothermal drilling operations using surface drilling parameters. The key parameters used for prediction include Rate of Penetration (ROP), Weight on Bit (WOB), Pump Pressure, Rotary Speed (RPM), Torque, and Flow Rate. Accurate prediction of rock types can significantly reduce the costs associated with well logging by providing real-time insights during the drilling process.

## Data Ingestion
The data for this project was obtained from the Utah FORGE Well 58-32 dataset, available on the Geothermal Data Repository (https://gdr.openei.org/). This dataset provides comprehensive surface drilling parameters necessary for our predictive modeling.

## Data Preparation
- Identified and treated outliers (using domain knowledge and a capping strategy) to ensure data quality and model performance.
- Ensured all data types were correctly formatted for analysis and modeling.

## Exploratory Data Analysis (EDA)
- **Rate of Penetration (ROP):** Higher ROP was observed in the Alluvium section compared to the Plutonic and Rhyolite sections.
- **Weight on Bit (WOB):** The Alluvium section required less WOB to achieve a faster ROP, whereas the Plutonic and Rhyolite sections needed more WOB.
- **Rotary Speed (RPM):** RPM was generally higher in the Alluvium section than in the other rock types.
- **Flow Rate:** Due to faster drilling rates in the Alluvium section, higher flow rates were required to manage the increased rock cuttings.

## Feature Engineering
- **Standardization:** All features were standardized using a Standard Scaler to ensure they are on the same scale and to improve model performance.

## Model Development
### Baseline Model
- Developed a baseline model using a Random Forest classifier.
- Conducted cross-validation to ensure robustness and generalizability of the baseline model.
- Evaluated the model using both training and test scores to detect any signs of overfitting.

### Model Optimization
- Utilized Bayesian Optimization with Tree-structured Parzen Estimator (TPE) to fine-tune the Random Forest model.
- Implemented a customized penalty score check within the optimization process to further mitigate overfitting risks.

## Acknowledgements
- Special thanks to the Utah FORGE team for providing the dataset.
- Gratitude to the open-source community for providing valuable tools and resources.

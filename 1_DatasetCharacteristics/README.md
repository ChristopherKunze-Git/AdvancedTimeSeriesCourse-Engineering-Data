# Dataset Characteristics

**[Notebook](EDA_Preprocessing.ipynb)**

### Databasis

Die Analyse basiert auf dem HUPA-UCM Diabetes Dataset, das Daten von 25 Patienten mit Typ-1-Diabetes über mehrere Tage enthält. Die Daten umfassen kontinuierliche Blutzuckermessungen, Insulindosierungen, Kohlenhydrataufnahmen sowie Fitness-Tracker-Daten (z. B. Schritte, Herzfrequenz, Kalorienverbrauch).

We use the HUPA-UCM Diabetes Dataset, which includes data from 25 individuals with Type 1 Diabetes Mellitus (T1DM). The dataset consists of:

- Continuous Glucose Monitoring (CGM) data (over several days, >7d)
- Fitness tracker data (steps, heart rate, burned calories, sleep)
- Carbohydrate intake and insulin dosages (basal + bolus)
- Preprocessed 5-minute interval data

### Exploratory Data Analysis (EDA) & Feature Engineering (FE)

Die Datenanalyse zeigte eine ungleiche Verteilung der Daten zwischen den Patienten, teils fehlende Werte und eine starke Korrelation zwischen bestimmten Variablen. Um die Qualität zu verbessern, wurden Imputationsmethoden wie lineare Interpolation und Multiple Imputation mit Chained Equations (MICE) eingesetzt. Außerdem wurden zeitabhängige Merkmale (sin/cos-codierte Tageszeit, Verzögerungen) ergänzt.

- The dataset is highly imbalanced: Over 50% of the data comes from a single subject (P27), and ~75% from just three subjects (P26, P27, P28).
- Some subjects have missing data (e.g., P15 lacks carbohydrate intake and bolus insulin records).
- Carbohydrate intake is recorded in different scales for different individuals.
- Severe cases of hypoglycemia (<70 mg/dL) and hyperglycemia (>180 mg/dL) are present.
- Missing data was linearly interpolated, and imputation was performed using "Multiple Imputation with Chained Equations" (MICE).


## Removed Features:

- Carbohydrate intake (high correlation with bolus insulin, but worse data quality)

- Steps (high correlation with burned calories)

## New Features:

- Time of day (sin/cos encoding for circadian rhythm)

- Lag features (e.g., 6-hour lag of glucose, heart rate, and insulin levels)


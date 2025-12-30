# UW–Madison MSDIA Healthcare Analytics
by Taran Schlichtmann 
Date: 09/07/2025

*Python-based healthcare analytics project for BMI and antibiotic dosage calculations.*

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](
https://colab.research.google.com/github/TaranSchlich/UW-Madison-MSDIA-Healthcare-Analytics/blob/main/notebooks/report.ipynb
)

## Overview
UW–Madison MSDIA project: Python-based healthcare data analysis for BMI calculation and antibiotic dosage determination. Includes:
- Data validation
- Unit conversions
- Conditional logic for outpatient clinical decision support

## Features
- Calculate BMI using CDC formula
- Compute adult amoxicillin dosage based on weight and age
- Demonstrates reproducibility and QA best practices

## Project Structure
```
UW-Madison-MSDIA-Healthcare-Analytics/
├─ notebooks/
│  └─ report.ipynb        # Colab notebook
├─ src/
│  └─ healthcare_bmi_dosage/
│     ├─ bmi.py           # BMI calculation logic
│     ├─ dosage.py        # Dosage calculation logic
├─ tests/
│  ├─ test_bmi.py         # Unit tests for BMI
│  └─ test_dosage.py      # Unit tests for dosage
├─ requirements.txt        # Python dependencies
├─ README.md               # Project documentation
```

## Quickstart
Clone the repo and install dependencies:
```bash
git clone https://github.com/TaranSchlich/UW-Madison-MSDIA-Healthcare-Analytics.git
cd UW-Madison-MSDIA-Healthcare-Analytics
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
```

Run tests:
```bash
pytest
```

## Usage Example
```python
from healthcare_bmi_dosage.bmi import bmi_from_imperial
from healthcare_bmi_dosage.dosage import amoxicillin_dose_mg, total_course_mg

bmi = bmi_from_imperial(weight_lb=181.39, height_ft=6.3)
dose = amoxicillin_dose_mg(weight_lb=181.39)
total = total_course_mg(age=45, weight_lb=181.39)
print(bmi, round(dose), round(total))
```

## Notes
- Conversion factor: `1 lb = 0.45 kg` (per assignment)
- For clinical precision, use `0.45359237`

## License
This project is licensed under the MIT License. See LICENSE for details.

**Disclaimer:** This project is for educational purposes only and should not be used for actual clinical decision-making.

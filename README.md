# Student Personality Identification Using Fuzzy Logic

ARTIFICIAL INTELLIGENCE | FUZZY LOGIC | PYTHON

A fuzzy logic project that applies the Tsukamoto and Sugeno inference methods to identify student personality types based on questionnaire responses. The project processes Likert-scale survey data, converts responses into a numerical domain, applies fuzzy membership functions and rule-based inference, and compares the resulting personality classifications.

## 01. Project Overview

### Project Description

This project, titled *Application of Fuzzy Tsukamoto and Sugeno Methods to Identify Students' Personality*, explores the use of fuzzy inference systems to classify student personality tendencies into four categories: Sanguinis, Koleris, Melankolis, and Plegmatis.

The system processes questionnaire responses using fuzzy membership functions, rule evaluation, and defuzzification or weighted output calculations. Three configurations are implemented: Tsukamoto, Sugeno Constant, and Sugeno Linear.

### Objectives

- Apply the Tsukamoto and Sugeno fuzzy inference methods to student questionnaire data.
- Convert Likert-scale responses into a numerical domain suitable for fuzzy processing.
- Define membership functions and rule-based inference for four personality categories.
- Compare personality classification distributions produced by the three configurations.
- Export the resulting personality scores and classifications to Excel files.

### Problem Statement

Understanding personality tendencies can help individuals reflect on their behavioral characteristics. However, questionnaire responses may represent different degrees of agreement rather than strictly binary conditions.

Fuzzy logic provides a framework for representing these degrees through membership functions and applying rule-based reasoning to numerical questionnaire responses.

### Dataset

The dataset was collected through a Google Forms questionnaire distributed to 50 students from the Informatics Study Program at the University of Mataram, class of 2022.

The questionnaire uses a five-point Likert scale, with responses converted into a numerical range of 0–150 by multiplying each score by 30.

The dataset contains 12 personality indicators:

| Personality Type | Indicators |
|---|---|
| Sanguinis | Keyakinan, Keramahan, Keberanian |
| Koleris | Emosi, Visioner, Penolong |
| Melankolis | Skeptis, Bimbang, Ego Sentrik |
| Plegmatis | Kerajinan, Kepekaan, Mudah Bosan |

Each respondent provides a score for all 12 indicators.

### Solution and Workflow

1. **Data Collection:** Collect questionnaire responses from 50 students.
2. **Data Conversion:** Convert Likert scores from 1–5 to values from 30–150.
3. **Fuzzification:** Calculate membership degrees using three input sets: Tidak Yakin, Ragu, and Yakin.
4. **Rule Evaluation:** Evaluate combinations of the three input membership levels for each personality category.
5. **Inference:** Apply the Tsukamoto or Sugeno output calculation.
6. **Personality Identification:** Compare the resulting scores across the four personality categories.
7. **Result Export:** Save calculated scores and classifications to Excel files.

### Fuzzy Configuration

**Input membership functions**

The input domain ranges from 0 to 150 and uses three triangular membership functions:

- Tidak Yakin
- Ragu
- Yakin

**Output membership functions**

The Tsukamoto implementation defines five output levels over a domain of 0–100:

- Sangat Rendah
- Rendah
- Sedang
- Tinggi
- Sangat Tinggi

The Sugeno implementation uses constant or linear consequent functions for the same five output levels.

## 02. Tech Stack

| Category | Technology |
|---|---|
| Programming Language | Python |
| Fuzzy Logic | scikit-fuzzy |
| Numerical Computing | NumPy |
| Data Processing | Pandas |
| Visualization | Matplotlib |
| Data Source | Google Forms questionnaire |
| Data Storage | Excel (`.xlsx`) |
| Development Environment | Jupyter Notebook |

### Implemented Methods

| Method | Description |
|---|---|
| Fuzzy Tsukamoto | Uses fuzzy rule activation and weighted output aggregation with the implemented output membership functions. |
| Sugeno Constant | Uses fixed consequent values for each output level. |
| Sugeno Linear | Calculates consequent values using linear functions of the three personality indicators. |

### Project Structure

```text
ml-FuzzyPersonalityClassification/
├── Assets/
│   ├── Fungsi Keanggotaan-output.png
│   └── Fungsi keangotaan.png
├── Dataset/
│   ├── hasil konversi_dataset_kepribadian_mahasiswa.xlsx
│   ├── konversiData.ipynb
│   └── survey_dataset fuzzy.xlsx
├── output/
│   ├── hasil_sugeno_constant.xlsx
│   ├── hasil_sugeno_linear.xlsx
│   └── hasil_tsukamoto.xlsx
├── fuzzyTsukamoto_Sugeno.ipynb
└── README.md
```

## 03. Screenshots / Results

### Workflow Visualizations

The project includes visualizations of the input and output membership functions. These plots illustrate how numerical questionnaire scores are mapped to fuzzy membership degrees.

- Input membership functions.
  <img width="846" height="470" alt="image" src="https://github.com/user-attachments/assets/d0448c46-16b4-4eab-96f9-c0eeaca7f59f" />

- Output membership functions.
  <img width="846" height="470" alt="image" src="https://github.com/user-attachments/assets/d8799124-81d7-4225-b575-ec3190e9c839" />

- Personality score distributions results.
  - TSUKAMOTO
    <img width="384" height="187" alt="image" src="https://github.com/user-attachments/assets/1754f172-7117-4fae-8af9-6333d7a5d3e6" />

  - SUGENO
    <img width="384" height="437" alt="image" src="https://github.com/user-attachments/assets/e7f73fc4-11e7-4d6f-903b-15babf6f40c7" />


### Personality Classification Results

The system processed 50 respondents using each of the three configurations.

**Experiment 1 — Fuzzy Tsukamoto**

| Personality Type | Respondents | Percentage |
|---|---:|---:|
| Sanguinis | 14 | 28% |
| Koleris | 14 | 28% |
| Melankolis | 10 | 20% |
| Plegmatis | 12 | 24% |
| **Total** | **50** | **100%** |

All 50 respondents received a personality classification under the implemented rules.

**Experiment 2 — Sugeno Constant**

| Personality Type | Respondents | Percentage |
|---|---:|---:|
| Sanguinis | 14 | 28% |
| Koleris | 14 | 28% |
| Melankolis | 10 | 20% |
| Plegmatis | 12 | 24% |
| **Total** | **50** | **100%** |

The reported classification distribution is identical to the Tsukamoto result.

**Experiment 3 — Sugeno Linear**

| Personality Type | Respondents | Percentage |
|---|---:|---:|
| Sanguinis | 13 | 26% |
| Koleris | 14 | 28% |
| Melankolis | 10 | 20% |
| Plegmatis | 13 | 26% |
| **Total** | **50** | **100%** |

Under the linear consequent configuration, Koleris was the most frequent classification, while Melankolis was the least frequent.

### Key Insights

- All three configurations produced classifications for 100% of the 50 respondents.
- Tsukamoto and Sugeno Constant produced the same reported personality distribution.
- Sugeno Linear produced a different distribution, with one fewer Sanguinis classification and one additional Plegmatis classification compared with the other two configurations.
- Koleris was the most frequent category in the Sugeno Linear results, representing 28% of respondents.
- Melankolis represented 20% of respondents in all three reported distributions.

### Usefulness

The project demonstrates how fuzzy inference can process questionnaire responses that represent varying degrees of agreement. Comparing different consequent configurations helps illustrate how the choice of inference method and output functions can influence the resulting classification distribution.

### Practical Application

Potential applications include:

- Educational demonstrations of fuzzy logic and rule-based inference.
- Research experiments comparing fuzzy inference configurations.
- Questionnaire analysis prototypes for exploring behavioral tendencies.
- Learning materials for implementing fuzzy systems in Python.

**Important limitation:** These classifications represent outputs from the project's implemented fuzzy rules, not clinically validated personality assessments. The results should not be used as definitive psychological diagnoses or as evidence that one method is more accurate without independent ground-truth labels and a suitable evaluation procedure.

## 04. Installation & Usage

### Prerequisites

- Python 3.9 or a compatible Python environment.
- Jupyter Notebook or JupyterLab.
- The original questionnaire dataset in Excel format.
- The required Python libraries.

### Installation

Clone the repository:

```bash
git clone https://github.com/YOUR_USERNAME/ml-FuzzyPersonalityClassification.git
cd ml-FuzzyPersonalityClassification
```

Install the required dependencies:

```bash
pip install pandas numpy scikit-fuzzy matplotlib openpyxl jupyter
```

### Running the Project

1. Place the original questionnaire file in the `Dataset/` directory.
2. Open `Dataset/konversiData.ipynb`.
3. Run the notebook cells to convert Likert scores from 1–5 into the 0–150 domain.
4. Verify that the converted dataset is saved as `hasil konversi_dataset_kepribadian_mahasiswa.xlsx` in the expected directory.
5. Open `fuzzyTsukamoto_Sugeno.ipynb`.
6. Verify the input file path and output directory configurations.
7. Run the notebook cells to define membership functions, evaluate fuzzy rules, and calculate personality scores.
8. Execute the Tsukamoto, Sugeno Constant, and Sugeno Linear implementations.
9. Review the resulting classifications and exported Excel files.

### Generated Output Files

| File | Description |
|---|---|
| `hasil_tsukamoto.xlsx` | Respondent scores and classifications produced by the Tsukamoto implementation. |
| `hasil_sugeno_constant.xlsx` | Respondent scores and classifications produced by Sugeno Constant. |
| `hasil_sugeno_linear.xlsx` | Respondent scores and classifications produced by Sugeno Linear. |

The output files contain the original converted indicators, calculated personality scores, and the resulting personality category.

### Notes

- Update file paths if the notebook's working directory differs from the repository root.
- The original survey contains 50 respondents and 12 indicators per respondent.
- The reported distributions are based on the provided implementation and should not be interpreted as validated personality ground truth.
- The fuzzy rules, membership functions, and Sugeno consequent parameters are predefined in the notebook rather than learned from labeled personality data.

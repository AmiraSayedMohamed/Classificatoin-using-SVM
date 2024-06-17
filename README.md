# 📊 Human Cell Classification using Support Vector Machine (SVM) 📈

## Overview

Welcome to the Human Cell Classification project! This project leverages Support Vector Machine (SVM) algorithms to classify human cell samples as either benign (mild state) or malignant (evil state). The goal is to create an accurate and robust model that can assist in medical diagnostics.

## Table of Contents

- [Introduction to SVM](#1--introduction-to-svm)
- [Necessary Imports](#2--necessary-imports)
- [About the Cancer Data](#3--about-the-cancer-data)
- [Load Data from CSV File](#4--load-data-from-csv-file)
- [Distribution of the Classes](#5--distribution-of-the-classes)
- [Identifying Unwanted Rows](#6--identifying-unwanted-rows)
- [Remove Unwanted Columns](#7--remove-unwanted-columns)
- [Divide the Data as Train/Test Dataset](#8--divide-the-data-as-traintest-dataset)
- [Modeling (SVM with Scikit-Learn)](#9--modeling-svm-with-scikit-learn)
- [Evaluation (Results)](#10--evaluation-results)

## 1- 🧠 Introduction to SVM
Used SVM to build and train a model using human cell records, and classify cells to whether the samples are benign (mild state) or malignant (evil state). SVM works by mapping data to a high-dimensional feature space so that data points can be categorized, even when the data are not otherwise linearly separable (This gets done by kernel function of SVM classifier). A separator between the categories is found, then the data is transformed in such a way that the separator could be drawn as a hyperplane.

## 2- 🔧 Necessary Imports
```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

3- 🏥 About the Cancer Data
Original Author - UCI Machine Learning Repository (Asuncion and Newman, 2007) [http://mlearn.ics.uci.edu/MLRepository]

Public Source - Cancer Data
Load Data From CSV File The characteristics of the cell samples from each patient are contained in fields Clump to Mit. The values are graded from 1 to 10, with 1 being the closest to benign.
The Class field contains the diagnosis, as confirmed by separate medical procedures, as to whether the samples are benign (value = 2) or malignant (value = 4).

row = record
column = attribute / dimension
target = prediction

4- 📂 Load Data from CSV File
python
Copy code
df = pd.read_csv("cell_samples.csv")
df.head()
ID	Clump	UnifSize	UnifShape	MargAdh	SingEpiSize	BareNuc	BlandChrom	NormNucl	Mit	Class
1000025	5	1	1	1	2	1	3	1	1	2
1002945	5	4	4	5	7	10	3	2	1	2
1015425	3	1	1	1	2	2	3	1	1	2
1016277	6	8	8	1	3	4	3	7	1	2
1017023	4	1	1	3	2	1	3	1	1	2


5- 📊 Distribution of the Classes

benign = df[df['Class']==2][0:200]
malignant = df[df['Class']==4][0:200]
benign.plot(kind='scatter', x='Clump', y='UnifSize', color='blue', label='Benign')
malignant.plot(kind='scatter', x='Clump', y='UnifSize', color='red', label='Malignant')





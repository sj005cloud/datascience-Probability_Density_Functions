# README
## Density Estimation Using Transformed NO2 Data

## Overview

This assignment uses n02 (Nitrogen Dioxide) values from an air quality dataset to estimate the parameters of a probability density function. The task involves transforming the NO2 values using a given formula and then learning the parameters of the density function from the transformed data.

---

## Feature Used

Only one feature from the dataset is used:

- NO2 concentration values

---

## Step 1: Transformation of NO2 Values

Each NO2 value (x) is transformed into a new variable (z) using the following transformation formula:

z = x + a × arcsin(b × x)

Where:

- x is the original NO2 value
- z is the transformed value
- arcsin represents the inverse sine function
- a = 0.05 × (r mod 7)
- b = 0.3 × ((r mod 5) + 1)
- r is the university roll number

For this assignment:

- Roll number (r): 102317173
- a = 0.1
- b = 1.2

Important implementation details:

- The value of (b × x) is restricted between -1 and 1 to ensure the arcsin function is valid.
- Any missing or NaN values in the dataset are removed before applying the transformation.

---

## Step 2: Probability Density Function Used

The probability density function used to model the transformed variable z is:

p̂(z) = c × exp(−λ × (z − μ)²)

Where:

- p̂(z) is the predicted probability of z
- μ (mu) is the mean of the transformed values
- λ (lambda) controls the spread of the distribution
- c is a normalization constant

---

## Step 3: Estimation of Parameters

The parameters are estimated using the following rules:

- μ (mu) is calculated as the mean of all transformed z values
- Variance is calculated from the transformed z values
- λ (lambda) is calculated as 1 divided by (2 × variance)
- c is calculated as the square root of (lambda divided by pi)

---

## Step 4: Results

The estimated parameters obtained from the transformed NO2 data are:

| Parameter | Value |
|----------|-------|
| mu       | 25.809622897811263 |
| lambda   | 0.001460436525489001 |
| c        | 0.021560876239314918 |

---

## Summary

- no2 values were transformed using the formula provided in the assignment.
- Constants a and b were computed using the university roll number.
- Missing values were removed and valid input range was ensured for transformation.
- Parameters mu, lambda, and c of the probability density function were successfully estimated.



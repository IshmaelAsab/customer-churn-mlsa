# Customer Churn Machine Learning and Survival Analysis

Applying machine learning and survival analysis to customer churn and time to event

## Overview

Traditional churn modelling commonly frames customer attrition as a binary classification problem:

- Churned = 1

- Not Churned = 0

While useful, this formulation does not directly model an important dimension of customer behaviour: **time**.

Survival analysis reframes the problem from simply asking:

> **Will this customer churn?**

to:

> **How long is the customer likely to remain active before churn?**

This project explores the application of survival analysis and machine learning techniques to telecom churn modelling.

## From Clinical Survival to Telecom Churn

Survival analysis is traditionally associated with clinical and medical research, where the objective is to model the time until an event occurs.

The same framework maps naturally to telecom:

| Clinical Trial | Business Churn |
|---|---|
| Patient | Customer |
| Admission date | Activation date |
| Death / event | Churn |
| Alive | Still active |
| Survival time | Time from activation to churn |
| Censored patient | Active customer whose churn time is unknown |

## The Time-to-Churn Problem

For a customer who churns:

**Survival Time = Churn Date − Activation Date**

The event is fully observed.

For a customer who remains active at the end of the observation period:

**Observed Time = Observation End Date − Activation Date**

However, this is **not the customer's final survival time**.

We only know that the customer has survived at least this long. The observation is therefore **right-censored**.

Survival analysis allows these incomplete customer lifecycles to contribute information without incorrectly treating the observation date as the churn date.

## Project Objectives

This project explores how survival methods is used to:

- Calculate customer survival time
- Identify and handle censored observations
- Estimate customer survival probabilities
- Analyse how churn risk changes over time
- Compare survival patterns across customer segments
- Identify factors associated with time to churn
- Apply machine learning methods to time-to-event prediction
- Support retention and customer lifecycle analytics

## Methods

The project include:

- Exploratory survival analysis
- Kaplan–Meier survival estimation
- Log-rank tests
- Cox proportional hazards regression
- Parametric survival models
- Machine-learning survival models
- Survival model evaluation and comparison

## Customer Features

Customer characteristics considered may include:

- Age
- Marital status
- Monthly charges
- Device type
- Internet service
- Contract type
- Payment method
- Technical support
- Online security
- Streaming services
- Customer tenure
- Activation date
- Churn date
- Churn status

## Survival Outcome

The core survival outcome consists of two variables:

**Time** — duration from customer activation until churn or the end of observation.
**Event** — indicates whether churn was observed.

- `Event = 1`: Customer churned
- `Event = 0`: Customer is right-censored

Together, these allow the model to distinguish between an observed churn event and a customer who is simply still active.

## Business Relevance

Rather than treating churn only as a Yes/No outcome, survival analysis enables telecom operators and other subscription-based businesses to investigate:

- Who is at risk of churn?
- When does churn risk increase?
- How long are customers likely to remain active?
- Which customer characteristics are associated with shorter or longer survival?
- How do survival patterns differ across products and customer segments?

The goal is to move from **churn classification** toward a richer understanding of the **customer lifecycle and time to attrition**.

## Repository Structure

```text
telecom-churn-survival-machine-learning/
├── data/
├── notebooks/
├── scripts/
├── results/
├── figures/
├── README.md

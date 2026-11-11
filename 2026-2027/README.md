# AI Methods for Business - Tutorials 2026-2027

Dear students,

This repository contains the tutorials for the AI for business course. Each practical is contained in a separate folder and consists of one or more jupyter notebooks. The notebooks are numbered in the order in which they should be completed.

## The Business case

A Dutch debt collection agency manages a portfolio of defaulted consumer debts.
Debtors have already missed payments. So the question is not *whether* they defaulted,
but what happens next:

- **Who will pay, and how much?** → determines which accounts to prioritise
- **Who will respond to contact?** → determines the contact strategy
- **Who is likely to dispute or complain?** → determines how carefully to handle the account

Right now these decisions are made by experience and gut feel. Our goal is to replace
gut feel with data-driven predictions. This tutorial lays the foundation:
understand the data, clean it, engineer features, and derive the targets that all
subsequent models will predict.

### The dataset

Four CSV files from the agency's own systems, covering accounts that defaulted
between 2020 and mid-2024:

| File | Rows | Description |
|---|---|---|
| `debtor_profiles.csv` | ~10,000 | One row per debtor. Demographics. |
| `accounts.csv` | ~14,000 | One row per debt account. Financial variables. |
| `payment_transactions.csv` | ~90,000 | One row per payment event. |
| `contact_history_enriched.csv` | ~111,000 | One row per contact attempt. Includes email and call text. |

### What we are predicting

| Target | Type | Window | Business question |
|---|---|---|---|
| `repayment_probability` | Binary classification | 90 days | Will this debtor make any payment? |
| `repayment_amount` | Regression | 90 days | How much will they pay in total? |
| `response_probability` | Binary classification | 30 days | Will this debtor respond to contact? |
| `complaint_risk` | Binary classification | No window | Will this debtor dispute or complain? |
| `time_to_repayment` | Regression (nullable) | no fixed window | How many days until first payment? |

All tutorials use the same dataset: the records of a debt collection agency, with its accounts, debtors, payments and every contact (email, letter, SMS, phone call, visit) between the agency and the debtors.

To be able to run these notebooks, you will first need to clone the repository on your local machine.

**The dataset is not in this repository.** Download `debt_collection_dataset_2026-27.zip` from the course page on Brightspace and save it in working directory. Please do not commit the data or share it outside the course.

You will then need to create a conda environment with the required dependencies. The dependencies are listed in the requirements.txt file in this folder. To install them in an existing conda environment, run the following command from a terminal after activating the environment:

```bash
pip install -r requirements.txt
```

When this is done, you should be able to run the jupyter notebooks in the newly created environment.

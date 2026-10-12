# AI Methods for Business - Tutorials 2026-2027

Dear students,

This repository contains the tutorials for the AI for business course. Each practical is contained in a separate folder and consists of one or more jupyter notebooks. The notebooks are numbered in the order in which they should be completed.

This year, all tutorials use the same dataset: the records of a debt collection agency, with its accounts, debtors, payments and every contact (email, letter, SMS, phone call, visit) between the agency and the debtors. `AI_Debt_Collection_Data_Schema.pdf`, included with the data, describes every table and column.

To be able to run these notebooks, you will first need to clone the repository on your local machine.

**The dataset is not in this repository.** Download `debt_collection_dataset_2026-27.zip` from the course page on Brightspace and unzip it inside this folder (`2026-2027/`). This creates `2026-2027/datasets/debt_collection/` with the four CSV files and the schema PDF, which is where the notebooks expect them. Please do not commit the data or share it outside the course.

You will then need to create a conda environment with the required dependencies. The dependencies are listed in the requirements.txt file in this folder. To install them in an existing conda environment, run the following command from a terminal after activating the environment:

```bash
pip install -r requirements.txt
```

When this is done, you should be able to run the jupyter notebooks in the newly created environment.

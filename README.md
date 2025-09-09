# data_engineering_pipeline_for_hospitals
RCM is the process that hospitals use to manage the financial aspects, from the time the patient schedules an appointment till the time the provider gets paid.

Technology - Azure Data Engineering Stack

Domain - Healthcare Revenue Cycle Management (RCM)

RCM is the process that hospitals use to manage the financial aspects, from the time the patient schedules an appointment till the time the provider gets paid..

Here is a simplified breakdown:

1. It starts with a patient visit:
 patient details are collected, Insurance details..
 This ensures provider knows who will pay for the services
 insurance, the patient, or both 

 20000 USD

 15000 USD - Insurance
 5000 USD - Patient


2. Services are provided


3. Billing happens: The hospital will create a bill.


4. Claims are reviewed: Insurance company review the bill

they might accept it, pay in full, or partial or decline.


5. Payments and followups

if partial payment is done by insurance company,

then some portion or complete thing is given by the patient...

and the providers will followup for the payment


6. Tracking and improvement: 

RCM ensures the hospital can provide quality care while also staying financially healthy.

Linked Services
================
- Azure SQL DB
- ADLS Gen2
- Delta Lake
- Key Vault (new one) done
- Databricks (new one) done


Datasets
=========
Azure SQL
Delimited text
Parquet
Databricks delta lake
EMR data to the bronze

claims and the NPI, ICD,CPT

Claims and CPT (landing -> bronze)

NPI and ICD codes (api -> bronze)

=> NPI code starts with 1, but in our datasets its different.

=> Data extracted from the API's is very less, so when you make join you may see lot of nulls.

Claims and CPT (landing -> bronze)

Bronze to Silver
=================
EMR Data
 - Patients SCD2
 - Providers (full load)
 - Department (full load)
 - Transactions SCD2
 - Encounters SCD2

Implement the silver layer

Clean / CDM / SCD2 / Delta tables

Implementing Gold Layer

Facts and Dims

Implementing Key vault

Improve the naming convensions

Make ADF pipeline parallel

API's

Claims Data

is_active flag implementation

Implement the Unity Catalog

Right now our catalog is a hive metastore which is local

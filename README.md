# Marketing Metrics Pipeline

This project demonstrates a data pipeline built with n8n, Supabase, and dbt to ingest, transform, and expose marketing performance metrics within a defined date range.

# Project Overview

## Ingestion:
Automated ingestion of raw marketing data via n8n workflow.
The workflow fetches metrics, processes them, and stores them into a Supabase Postgres database.

## Transformation:
Data transformations are managed using dbt models.
The models calculate key performance indicators such as:

- Spend in last and prior periods
- CAC (Customer Acquisition Cost)
- ROAS (Return on Ad Spend)
- Period-over-period deltas

## Output:
Results are exposed via:
- A Supabase table (queryable API endpoint)
- Aditionally, an .xlsx export stored in Supabase Storage with a public download link

# Requeriments if you want to use your own Supabase account
- Create a new account into Supabase if you don't have one. [Supabase site](https://supabase.com/). The following is the home screen:
<img width="1710" height="783" alt="image" src="https://github.com/user-attachments/assets/3601dcac-b74b-43a1-87da-2df4e2b4dfad" />

  
- Create a table. Go to your project -> SQL Editor -> create a table using the SQL that I provided you.
<img width="443" height="480" alt="image" src="https://github.com/user-attachments/assets/f95c3e6e-a7da-4547-a017-f0b7a0c41847" />

  
- Once you create a table, Go to Connect -> Session pooler -> Get Host, user, password, database, port values and save them to create a postgres credential in n8n.
<img width="1243" height="746" alt="image" src="https://github.com/user-attachments/assets/544f22e3-05dd-45ad-802d-18899221294e" />

- Create a public bucket into Supabase. Go to your project -> Storage Menu -> New bucket -> Enter Bucket name, configure as public bucket, create.
  Here you can save files and other things.
<img width="569" height="761" alt="image" src="https://github.com/user-attachments/assets/4330fd5a-a6b8-426d-b10d-1dd84de9da2d" />

- Get API KEYS in Supabase. Go to project -> Project settings Menu -> Data API, to get Host URL value -> Api Keys, to get service role secret. Save them values to create a HTTP credential in n8n.
<img width="1287" height="758" alt="image" src="https://github.com/user-attachments/assets/9a10ae75-a98a-4c38-bf5a-3013b8cddc87" />

- You can import Postman collection to your own Postman to consume the solution

# Installation

Considering this test, you need to:
- Import a .json file into your n8n environment
- Entry the Postgress database (Supabase DB) credentials in 'Data Range Metrics', 'Compare last 30 days vs prior 30 days', 'Insert or update rows in a table' Nodes. (is the same credential)
- Entry the API Keys Supabase credentials into 'HTTP Request' node.
- Use Postman or your browser to check the functionality.


Any doubts contact me!

Regards

# Microsoft Fabric Sales Pipeline Project

## Overview
This project demonstrates an end-to-end ETL workflow in **Microsoft Fabric** using:
- **Data Pipeline** (Delete + Copy Data + Notebook)
- **Lakehouse** (Files + Delta tables)
- **PySpark Notebook** for transformation and loading

The goal is to ingest a CSV file from HTTP, transform it, and load it into a queryable table.

---

## Architecture Flow
HTTP CSV Source  
→ Copy Data Activity  
→ Lakehouse Files (`Files/new_data/sales.csv`)  
→ Notebook Transformation (PySpark)  
→ Delta Table (`sales` / `new_sales`)

---

## Source Dataset
- URL: https://raw.githubusercontent.com/MicrosoftLearning/dp-data/main/sales.csv

---

## Steps Performed

1. Created workspace and lakehouse in Microsoft Fabric.
2. Created folder `new_data` under Lakehouse Files.
3. Built pipeline **Ingest Sales Data** with:
   - Delete old files
   - Copy data from HTTP source
   - Run notebook activity
4. Created notebook **Load Sales** with:
   - parameter cell (`table_name`)
   - PySpark transformations
   - Delta write using `saveAsTable`
5. Ran and validated outputs in Lakehouse Tables.

---

## Files in this Repository

- `pipeline-configuration.md` → Pipeline settings used in Fabric
- `notebook-code.md` → Notebook code used for transformation/load
- `screenshots/` → Execution proof (pipeline, notebook, table preview)

---

## Skills Demonstrated
- Microsoft Fabric Lakehouse
- Data Pipeline orchestration
- HTTP ingestion
- PySpark data transformation
- Delta table loading
- Parameterized notebook execution

---

## Author
**Yashwitha-valmiki**

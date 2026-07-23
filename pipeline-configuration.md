# Pipeline Configuration (Microsoft Fabric)

## Pipeline Name
Ingest Sales Data

## Activities
1. Delete old files
2. Copy data
3. Load Sales notebook

## 1) Delete old files
- Connection: Lakehouse
- File path type: Wildcard file path
- Folder path: `Files/new_data`
- Wildcard file name: `*.csv`
- Recursive: Enabled
- Logging: Disabled

## 2) Copy data

### Source
- Connector: HTTP
- URL: `https://raw.githubusercontent.com/MicrosoftLearning/dp-data/main/sales.csv`
- Authentication: Anonymous
- File format: DelimitedText
- Delimiter: Comma (,)
- Row delimiter: Line feed (\n)
- First row as header: Enabled

### Destination
- Target: Lakehouse
- Root folder: `Files`
- Directory: `new_data`
- File name: `sales.csv`

## 3) Notebook activity
- Notebook name: `Load Sales`
- Base parameter:
  - `table_name` = `dbo.new_sales` (or `dbo.sales` for initial run)

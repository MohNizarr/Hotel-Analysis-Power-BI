# Hotel Booking Data Analysis: ETL with Pentaho and Dashboard on Power BI

This project demonstrates an **End-to-End Business Intelligence (BI)** workflow for analyzing hotel booking data, starting from raw data (`.csv`), ETL orchestration using **Pentaho Data Integration (Kettle)**, data loading into a **SQL Data Warehouse**, and culminating in interactive visualization using **Power BI**.

-----

## Key Features

  * **Initial Data Processing (CSV):** Analyzes raw hotel booking data originating from a CSV file.
  * **Comprehensive ETL Transformation:** Uses Pentaho Data Integration (Kettle) to perform:
      * **Extraction:** Retrieves data from the CSV source.
      * **Transformation:** Performs data cleaning, data enrichment (e.g., date dimension creation), and normalization.
      * **Loading:** Loads dimension and fact data into a SQL-based Data Warehouse.
  * **Data Warehouse (SQL):** Provides a SQL database schema for storing data in a **star schema** model, consisting of a Fact Booking table and dimension tables (Customer, Room Type, Date, etc.).
  * **Interactive Visualization:** Generates a comprehensive BI Dashboard using Power BI to analyze booking trends, occupancy rates, revenue, and customer segmentation.

-----

## Technology Used

| Category | Technology | Description |
| :--- | :--- | :--- |
| **Data Source** | CSV | The initial raw hotel booking data. |
| **ETL/Orchestration** | Pentaho Data Integration (PDI) / Kettle | Used to build the ETL Transformations and Jobs. |
| **Data Warehouse** | SQL Database (e.g., MySQL, PostgreSQL) | Used to store the transformed dimension and fact data. |
| **BI Visualization** | Power BI | Used to construct the final interactive dashboard. |

-----

## Installation Prerequisites

To run and replicate this project, you will need the following software:

1.  **Pentaho Data Integration (Kettle):** Used to open and run the `.ktr` (Transformation) and `.kjb` (Job) files.
2.  **SQL Database System:** A database server (e.g., MySQL or PostgreSQL) to host the Data Warehouse.
3.  **Power BI Desktop:** Used to open the final report file (`.pbix`).

### Database Setup

You must create the Data Warehouse schema in your SQL database:

1.  Create a new database (e.g., `dw_hotel`).
2.  Execute the SQL script in `Datasets/dw_hotel.sql` to create all dimension tables (`dim_customer`, `dim_date`, etc.) and the fact table (`fact_booking`).

-----

## Project Structure

```
.
├── Datasets/
│   ├── dw_hotel.sql             # SQL script to create the Data Warehouse (Star Schema).
│   ├── hotel.sql                # SQL script for raw source data.
│   ├── hotel.ktr                # Pentaho Transformation (Initial ETL step from CSV/SQL).
│   ├── dim_customer.ktr         # Pentaho Transformation for loading Customer Dimension.
│   ├── dim_date.ktr             # Pentaho Transformation for loading Date Dimension.
│   ├── fact_booking.ktr         # Pentaho Transformation for loading the Booking Fact Table.
│   └── (Other dimension .ktr files...)
├── Laporan Hasil Pemesanan Hotel.pbix # Final Power BI Dashboard file.
└── README.md
```

-----

## Example Usage

Steps to run this end-to-end analysis:

1.  **Configure Pentaho:** Open each `.ktr` file in Pentaho Data Integration and update your database connection configurations (e.g., the connection details for your `dw_hotel` database).
2.  **Run ETL:** Execute the Pentaho Transformations in order (Dimensions first, then Facts) to load data from the source into your SQL Data Warehouse.
3.  **Open Power BI:** Open the `Laporan Hasil Pemesanan Hotel.pbix` file.
4.  **Refresh Data:** In Power BI, refresh the data to connect to and retrieve the newly loaded data from your SQL database. Ensure the Power BI database connection details are correct.
5.  **Analyze:** Explore the interactive dashboard to gain insights into hotel occupancy rates, sales performance, and booking trends.

-----

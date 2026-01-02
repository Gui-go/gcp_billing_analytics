# GCP Billing Analytics

This project provides a comprehensive framework for analyzing Google Cloud Platform (GCP) billing data. By leveraging the GCP Billing Export feature, this project allows you to gain deep insights into your cloud spending, identify cost-saving opportunities, and optimize your resource usage.

## About GCP Billing Export

GCP Billing Export is a feature that allows you to export your detailed Google Cloud billing data to BigQuery for in-depth analysis. This can help you to better understand your costs, identify trends, and optimize your cloud spending.

### Key Features and Benefits:

*   **Detailed Data:** You can export standard usage cost data, which includes information like account ID, invoice date, services, SKUs, projects, labels, locations, cost, usage, credits, and adjustments. For more granular analysis, you can export detailed usage cost data, which provides resource-level information.
*   **Pricing Data:** You can also export your Cloud Billing account pricing information.
*   **BigQuery Integration:** By exporting your data to BigQuery, you can run powerful SQL queries to analyze your costs in a customized way. BigQuery is a serverless, highly scalable data warehouse that allows you to analyze large datasets quickly.
*   **Visualization:** You can use tools like Looker Studio to create custom dashboards and visualize your billing data, making it easier to understand and share with stakeholders.
*   **Cost Optimization:** Detailed analysis of your billing data can help you identify areas where you can optimize your costs.

## Project Structure

This project is structured as a dataform project, with the following directories:

*   `definitions/`: Contains the SQLX files that define the data transformation pipelines.
    *   `sources/`: Defines the raw data sources from the GCP Billing Export.
    *   `staging/`: Cleans and prepares the raw data for further processing.
    *   `intermediate/`: Creates intermediate tables with aggregated and enriched data.
    *   `mart/`: Creates the final data marts for analysis and reporting.
*   `workflow_settings.yaml`: Contains the settings for the dataform workflow.

## Data Pipelines and Models

This project implements a series of data pipelines to process and analyze the GCP billing data. The pipelines are defined using SQLX files in the `definitions/` directory.

The project also includes several machine learning models to provide advanced analytics and recommendations:

*   **BQML Models:** The project uses BigQuery ML (BQML) to build and train machine learning models for forecasting, clustering, and anomaly detection.
*   **Generative AI:** The project leverages a Gemini model to generate detailed cost optimization reports and recommendations. The `genai_service_suggestions.sqlx` file contains a query that uses the `ML.GENERATE_TEXT` function to generate a technical report with actionable insights.

## How to Use This Project

To use this project, you will need to:

1.  **Set up GCP Billing Export:** Follow the instructions in the [GCP documentation](https.cloud.google.com/billing/docs/how-to/export-data-bigquery) to enable billing export to a BigQuery dataset.
2.  **Configure Dataform:** Update the `workflow_settings.yaml` file with your GCP project ID, BigQuery dataset, and other relevant settings.
3.  **Run Dataform:** Run the dataform pipelines to process your billing data and generate the analytics tables.
4.  **Explore the Data:** Use BigQuery to query the data marts and explore your cloud spending. You can also connect a BI tool like Looker Studio to create interactive dashboards.
5.  **Generate Recommendations:** Run the `genai_service_suggestions.sqlx` query to generate a detailed cost optimization report.






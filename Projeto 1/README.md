# 📊 Power BI for Data Analytics - Project about analysis of Data Jobs available globally in 2024

A bit of initial information: This is a project about visualizing data of jobs postings related to Data Fields in 2024.

### Page 1: High-Level Market View
![Dashboard Page 1](/images/Data_Dashboard_Page1.png)
Page 1 is showcases KPIs like total available jobs right now, a rating of the median salaries compared to our desired range of salaries, yearly/hourly median salaries and top job titles to give a quick understanding at a glance.

### Page 2: Job Title Drill-Through
![Dashboard Page 2](/images/Data_Dashboard_Page2.png)
Page 2 allows to get a more in-depth look at a certain role. Including salary ranges, work-from-home stats, top hiring platforms, and a global map of job locations.

### Dashboard File
You can find the file for the dashboard here: [`Visualizations_Dashboard.pbix`](Visualizations_Dashboard.pbix).

## Skills Showcased

This project was a journey through key Power BI features. Here's a look at what we mastered:

-   **⚙️ Data Transformation (ETL) with Power Query:** Cleaned, shaped, and prepared the raw data for analysis by handling blanks, changing data types, and creating new columns.
-   **🧮 Implicit Measures:** Formulated measures to derive key insights and KPIs like `Median Yearly Salary` and `Job Count`.
-   **📊 Core Charts:** Utilized **Column, Bar, Line,** and **Area Charts** to compare job counts and track trends over time.
-   **🗺️ Geospatial Analysis:** Leveraged **Map Charts** to visualize the global distribution of jobs.
-   **🔢 KPI Indicators & Tables:** Used **Cards** to display key metrics and **Tables** to provide granular, sortable data.
-   **🎨 Dashboard Design:** Designed an intuitive and visually appealing layout, exploring both common and uncommon chart types to best tell the data story.
-   **🖱️ Interactive Reporting:**
    -   **Slicers:** To dynamically filter the report by Job Title.
    -   **Buttons & Bookmarks:** To create a seamless navigation experience.
    -   **Drill-Through:** To navigate from a high-level summary to a contextual, detailed view.

## Data files

- `job_postings_flat.csv` - A CSV file that contains the data for the job postings in one single table.


## 📘 Data Dictionary

| Column Name             | Description                                                                 | Type         | Source           |
|-------------------------|-----------------------------------------------------------------------------|--------------|------------------|
| `job_title_short`       | Cleaned/standardized job title using BERT model (10-class classification)   | Calculated   | From `job_title` |
| `job_title`             | Full original job title as scraped                                          | Raw          | Scraped          |
| `job_location`          | Location string shown in job posting                                        | Raw          | Scraped          |
| `job_via`               | Platform the job was posted on (e.g., LinkedIn, Jobijoba)                   | Raw          | Scraped          |
| `job_schedule_type`     | Type of schedule (Full-time, Part-time, Contractor, etc.)                   | Raw          | Scraped          |
| `job_work_from_home`    | Whether the job is remote (`true`/`false`)                                  | Boolean      | Parsed           |
| `search_location`       | Location used by the bot to generate search queries                         | Generated    | Bot logic        |
| `job_posted_date`       | Date and time when job was posted                                           | Raw          | Scraped          |
| `job_no_degree_mention` | Whether the posting explicitly mentions no degree is required               | Boolean      | Parsed           |
| `job_health_insurance`  | Whether the job mentions health insurance                                   | Boolean      | Parsed           |
| `job_country`           | Country extracted from job location                                         | Calculated   | Parsed           |
| `salary_rate`           | Indicates if salary is annual or hourly                                     | Raw          | Scraped          |
| `salary_year_avg`       | Average yearly salary (calculated from salary ranges when available)        | Calculated   | Derived          |
| `salary_hour_avg`       | Average hourly salary (same logic as yearly)                                | Calculated   | Derived          |
| `company_name`          | Company name listed in job posting                                          | Raw          | Scraped          |
| `job_skills`            | List of relevant skills extracted from job posting using PySpark            | Parsed List  | NLP Extracted    |
| `job_type_skills`       | Dictionary mapping skill types (e.g., 'cloud', 'libraries') to skill sets   | Parsed Dict  | NLP Extracted    |

## Conclusion

This dashboard showcases how Power BI can transform raw job posting data into a powerful tool for career analysis. It allows users to slice, filter, and drill through data to make informed decisions about their career paths.
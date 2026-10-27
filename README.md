# Formula 1 Big Data Analysis using PySpark

**A Formula 1 race-data analytics project built with PySpark, Apache
Spark, Spark SQL, and Python.**

## Overview

F1 DataLab explores Formula 1 race-level data to identify patterns in
driver performance, race outcomes, pole positions, podium finishes,
safety-car periods, and season-wise trends.

The project uses PySpark to load and inspect CSV data, clean records,
perform aggregations, query with Spark SQL, save data in Parquet format,
and visualize selected results. The notebook is designed to run in
Google Colab.

## Objectives

-   Inspect and validate a Formula 1 race-results dataset.
-   Rank drivers by recorded race wins and podium finishes.
-   Analyze pole positions and pole-to-win conversion.
-   Explore race counts and safety-car patterns across seasons,
    circuits, and regions.
-   Compare sprint-weekend and non-sprint-weekend records.
-   Demonstrate PySpark DataFrames, transformations, aggregations, and
    Spark SQL.
-   Save processed data as Parquet and compare query timings with CSV.

## Technology stack

-   **Language:** Python
-   **Big Data processing:** Apache Spark, PySpark
-   **Querying:** Spark SQL
-   **Visualization:** Matplotlib
-   **Data formats:** CSV, Parquet
-   **Environment:** Google Colab

## Dataset

The supplied `race_results.csv` contains **337 rows and 15 columns** in
the version used to develop this project.

  Column                 Description
  ---------------------- ---------------------------------------
  `race_id`              Race identifier
  `season`               Championship season
  `round_number`         Round number within the season
  `race_date`            Race date
  `grand_prix`           Grand Prix name
  `circuit`              Circuit name
  `country_iso3`         Three-letter country code
  `region`               Geographic region
  `pole_position`        Driver recorded as starting on pole
  `winner`               Race winner
  `podium_p2`            Second-place finisher
  `podium_p3`            Third-place finisher
  `fastest_lap_driver`   Driver recorded as fastest-lap holder
  `safety_car_periods`   Number of safety-car periods
  `is_sprint_weekend`    Sprint-weekend indicator (0/1)

**Dataset source:** Add the original source/download URL here before
publishing, along with any applicable license or attribution.

> **Data limitations:** This is race-level data, not detailed lap-by-lap
> telemetry. It does not include individual lap times, constructor
> names, championship points, or detailed qualifying times. It cannot
> independently support average lap-time analysis or verified
> constructor championship standings. Validate historical records before
> presenting results as definitive Formula 1 statistics.

## Analyses

### Driver performance

-   Rank drivers by recorded race wins.
-   Identify drivers with the most podium finishes.
-   Count seasons in which drivers recorded wins or podiums.

### Pole-position analysis

-   Rank drivers by recorded pole positions.
-   Calculate how often a recorded pole-sitter also won the race.

### Season trends

-   Count recorded races per season.
-   Examine safety-car periods across seasons.

### Circuit and regional patterns

-   Identify circuits appearing most often in the dataset.
-   Compare average safety-car periods by circuit and region.

### Sprint-weekend comparison

-   Compare safety-car statistics for sprint and non-sprint weekends.
-   Compare pole-to-win conversion rates by weekend type.

### Storage and performance

-   Save cleaned data in Parquet format.
-   Compare CSV and Parquet query execution times under the same
    conditions.

## PySpark concepts demonstrated

-   `SparkSession` initialization
-   CSV ingestion and schema inspection
-   Data cleaning and type conversion
-   Filtering and sorting
-   `groupBy()` and aggregations
-   Reshaping data with `explode()`
-   Temporary views and Spark SQL
-   Parquet storage
-   Basic query-time benchmarking

## Visualizations

The notebook can produce charts for: - Top drivers by recorded race
wins - Recorded races per season - Average safety-car periods by
region - Sprint versus non-sprint safety-car comparison - Top drivers by
recorded podium finishes

Add screenshots of the actual generated charts after running the
notebook.

## Getting started

### Google Colab

1.  Upload `F1_Big_Data_Analysis.ipynb` to Google Colab.
2.  Run the installation and Spark initialization cell.
3.  Upload `race_results.csv` when prompted, or update the file path.
4.  Run the notebook cells in order.
5.  Review the analysis tables, charts, and CSV-versus-Parquet timing
    results.

### Run locally

Install dependencies:

``` bash
pip install -r requirements.txt
```

Launch Jupyter:

``` bash
jupyter notebook
```

Open the notebook and ensure the dataset path matches the location of
`race_results.csv`.



## Benchmark notes

The notebook includes a basic CSV-versus-Parquet query-time comparison.
Results can vary due to caching, data size, runtime conditions, and
Spark overhead. Because the supplied dataset is small, treat timings as
an educational experiment rather than a general performance claim. For a
stronger benchmark, repeat the experiment with a larger dataset and
equivalent queries.

## Limitations and future improvements

Current limitations: - Uses race-level rather than lap-by-lap data. -
Does not contain constructor, points, pit-stop, or detailed qualifying
fields. - Historical records require validation. - Google Colab normally
runs Spark in a single runtime; this project does not claim to benchmark
a multi-node cluster.

Possible extensions: - Integrate a validated lap-times dataset. - Add
qualifying and pit-stop analysis using additional sources. - Add
constructor and championship-points analysis when the necessary fields
are available. - Benchmark with a larger dataset. - Explore more
advanced statistical analysis.

## Author

**Abdul Rehan**

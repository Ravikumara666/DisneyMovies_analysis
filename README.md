<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Disney Movies Analysis - Project README</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f7f7f7;
            margin: 0;
            padding: 0;
        }
        header {
            background-color: #0047ab;
            color: white;
            padding: 15px 0;
            text-align: center;
        }
        .container {
            max-width: 900px;
            margin: 20px auto;
            padding: 20px;
            background-color: white;
            border-radius: 10px;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
        }
        h1, h2, h3 {
            color: #333;
        }
        h2 {
            font-size: 1.5em;
            margin-top: 20px;
        }
        p {
            font-size: 1em;
            line-height: 1.6;
            margin-bottom: 15px;
        }
        code {
            display: block;
            background-color: #f4f4f4;
            padding: 15px;
            border-radius: 5px;
            font-family: Consolas, monospace;
            color: #333;
            margin-top: 10px;
            white-space: pre-wrap;
        }
        .feature-list {
            list-style-type: none;
            padding: 0;
        }
        .feature-list li {
            background-color: #f1f1f1;
            padding: 10px;
            margin: 10px 0;
            border-radius: 5px;
            box-shadow: 0 1px 4px rgba(0, 0, 0, 0.1);
        }
        .tech-stack ul {
            list-style-type: none;
            padding: 0;
            margin: 0;
        }
        .tech-stack li {
            background-color: #e9ecef;
            padding: 8px;
            margin: 5px 0;
            border-radius: 4px;
        }
        .installation ul {
            padding: 0;
        }
        .installation li {
            margin: 5px 0;
        }
        .code-snippet {
            background-color: #282c34;
            color: white;
            padding: 15px;
            border-radius: 5px;
            margin-top: 15px;
        }
        .installation li span {
            font-weight: bold;
        }
    </style>
</head>
<body>

<header>
    <h1>Disney Movies Analysis - Big Data Project</h1>
</header>

<div class="container">
    <h2>Overview</h2>
    <p>This project analyzes Disney movies and shows data, using Big Data tools like PySpark to perform year-wise analysis and gain insights from the dataset. The data is processed, cleaned, and visualized to understand patterns such as distribution across years, genres, and other characteristics of Disney movies available on the Disney+ platform.</p>
    
    <h2>Features</h2>
    <ul class="feature-list">
        <li>Data Cleaning & Preprocessing: Handling missing values and preparing data for analysis.</li>
        <li>Big Data Processing: Utilizes PySpark for efficient processing of large datasets.</li>
        <li>Year-wise Analysis: Analyzes and visualizes the number of movies per year, genre trends, etc.</li>
        <li>Data Visualization: Interactive charts and insights to present key findings.</li>
        <li>Analysis of Missing Data: Identification of missing values across various columns.</li>
    </ul>

    <h2>Technology Stack</h2>
    <div class="tech-stack">
        <ul>
            <li><strong>Hardware:</strong> N/A (Big Data Processing)</li>
            <li><strong>Backend:</strong> PySpark for data processing</li>
            <li><strong>Libraries:</strong> confluent-kafka, PySpark, Pandas, Matplotlib</li>
            <li><strong>Frontend:</strong> N/A</li>
            <li><strong>Programming Languages:</strong> Python</li>
        </ul>
    </div>

    <h2>How It Works</h2>
    <p>The project uses PySpark to read and analyze the dataset containing Disney movies and shows. Data is read from a CSV file, cleaned, and then analyzed year-wise to extract valuable insights.</p>
    
    <h3>Steps:</h3>
    <ul>
        <li>Step 1: Install required libraries like PySpark and confluent-kafka.</li>
        <li>Step 2: Load the dataset using PySpark.</li>
        <li>Step 3: Clean the data by checking for null values.</li>
        <li>Step 4: Analyze the data and perform year-wise analysis.</li>
        <li>Step 5: Generate insights and visualizations based on the cleaned dataset.</li>
    </ul>
    
    <h2>Installation and Setup</h2>
    <p>Follow the steps below to set up this project:</p>
    <div class="installation">
        <ul>
            <li><span>Step 1:</span> Install PySpark and confluent-kafka:</li>
            <code class="code-snippet">!pip install confluent-kafka</code>

            <li><span>Step 2:</span> Install PySpark in your environment:</li>
            <code class="code-snippet">!pip install pyspark</code>

            <li><span>Step 3:</span> Ensure that your environment is configured with the necessary dependencies for PySpark.</li>

            <li><span>Step 4:</span> Clone the repository and start analyzing the data using the provided Python scripts.</li>
        </ul>
    </div>

    <h2>Code Snippet</h2>
    <p>Here is an example of how data is processed and missing values are analyzed:</p>
    <code class="code-snippet">
import pyspark
from pyspark.sql import SparkSession
from pyspark.sql.functions import count, col, when, desc, max, asc, avg, round

spark = SparkSession.builder.appName("Disney Data Analysis").getOrCreate()
df = spark.read.csv("disney_plus_shows.csv", header=True, inferSchema=True)
df.select([count(when(col(c).isNull(), 1)) for c in df.columns]).show()
    </code>

</div>

</body>
</html>

<div style="font-family: Arial, sans-serif; background-color: #f7f7f7; margin: 0; padding: 0;">
    <header style="background-color: #0047ab; color: white; padding: 15px 0; text-align: center;">
        <h1>Disney Movies Analysis - Big Data Project</h1>
    </header>
<div style="max-width: 900px; margin: 20px auto; padding: 20px; background-color: white; border-radius: 10px; box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);">
        <h2 style="color: #333; font-size: 1.5em;">Overview</h2>
        <p style="font-size: 1em; line-height: 1.6; margin-bottom: 15px;">This project analyzes Disney movies and shows data, using Big Data tools like PySpark to perform year-wise analysis and gain insights from the dataset. The data is processed, cleaned, and visualized to understand patterns such as distribution across years, genres, and other characteristics of Disney movies available on the Disney+ platform.</p>
 <h2 style="color: #333; font-size: 1.5em;">Features</h2>
        <ul style="list-style-type: none; padding: 0;">
            <li style="background-color: #f1f1f1; padding: 10px; margin: 10px 0; border-radius: 5px; box-shadow: 0 1px 4px rgba(0, 0, 0, 0.1);">Data Cleaning & Preprocessing: Handling missing values and preparing data for analysis.</li>
            <li style="background-color: #f1f1f1; padding: 10px; margin: 10px 0; border-radius: 5px; box-shadow: 0 1px 4px rgba(0, 0, 0, 0.1);">Big Data Processing: Utilizes PySpark for efficient processing of large datasets.</li>
            <li style="background-color: #f1f1f1; padding: 10px; margin: 10px 0; border-radius: 5px; box-shadow: 0 1px 4px rgba(0, 0, 0, 0.1);">Year-wise Analysis: Analyzes and visualizes the number of movies per year, genre trends, etc.</li>
            <li style="background-color: #f1f1f1; padding: 10px; margin: 10px 0; border-radius: 5px; box-shadow: 0 1px 4px rgba(0, 0, 0, 0.1);">Data Visualization: Interactive charts and insights to present key findings.</li>
            <li style="background-color: #f1f1f1; padding: 10px; margin: 10px 0; border-radius: 5px; box-shadow: 0 1px 4px rgba(0, 0, 0, 0.1);">Analysis of Missing Data: Identification of missing values across various columns.</li>
        </ul>
 <h2 style="color: #333; font-size: 1.5em;">Technology Stack</h2>
        <div>
            <ul style="list-style-type: none; padding: 0; margin: 0;">
                <li style="background-color: #e9ecef; padding: 8px; margin: 5px 0; border-radius: 4px;">Hardware: N/A (Big Data Processing)</li>
                <li style="background-color: #e9ecef; padding: 8px; margin: 5px 0; border-radius: 4px;">Backend: PySpark for data processing</li>
                <li style="background-color: #e9ecef; padding: 8px; margin: 5px 0; border-radius: 4px;">Libraries: confluent-kafka, PySpark, Pandas, Matplotlib</li>
                <li style="background-color: #e9ecef; padding: 8px; margin: 5px 0; border-radius: 4px;">Frontend: N/A</li>
                <li style="background-color: #e9ecef; padding: 8px; margin: 5px 0; border-radius: 4px;">Programming Languages: Python</li>
            </ul>
        </div>
 <h2 style="color: #333; font-size: 1.5em;">How It Works</h2>
        <p style="font-size: 1em; line-height: 1.6; margin-bottom: 15px;">The project uses PySpark to read and analyze the dataset containing Disney movies and shows. Data is read from a CSV file, cleaned, and then analyzed year-wise to extract valuable insights.</p>
        <h3 style="color: #333; font-size: 1.3em;">Steps:</h3>
        <ul style="font-size: 1em; line-height: 1.6; margin-bottom: 15px;">
            <li>Step 1: Install required libraries like PySpark and confluent-kafka.</li>
            <li>Step 2: Load the dataset using PySpark.</li>
            <li>Step 3: Clean the data by checking for null values.</li>
            <li>Step 4: Analyze the data and perform year-wise analysis.</li>
            <li>Step 5: Generate insights and visualizations based on the cleaned dataset.</li>
        </ul>
         <h2 style="color: #333; font-size: 1.5em;">Installation and Setup</h2>
        <p style="font-size: 1em; line-height: 1.6; margin-bottom: 15px;">Follow the steps below to set up this project:</p>
        <div>
            <ul style="font-size: 1em; line-height: 1.6; margin-bottom: 15px;">
                <li><strong>Step 1:</strong> Install PySpark and confluent-kafka:</li>
                <pre style="background-color: #282c34; color: white; padding: 15px; border-radius: 5px; margin-top: 10px;">!pip install confluent-kafka</pre>
<li><strong>Step 2:</strong> Install PySpark in your environment:</li>
                <pre style="background-color: #282c34; color: white; padding: 15px; border-radius: 5px; margin-top: 10px;">!pip install pyspark</pre>
<li><strong>Step 3:</strong> Ensure that your environment is configured with the necessary dependencies for PySpark.</li>

 <li><strong>Step 4:</strong> Clone the repository and start analyzing the data using the provided Python scripts.</li>
</ul>
        </div>
 <h2 style="color: #333; font-size: 1.5em;">Code Snippet</h2>
        <p style="font-size: 1em; line-height: 1.6; margin-bottom: 15px;">Here is an example of how data is processed and missing values are analyzed:</p>
        <pre style="background-color: #282c34; color: white; padding: 15px; border-radius: 5px; margin-top: 10px;">
import pyspark
from pyspark.sql import SparkSession
from pyspark.sql.functions import count, col, when, desc, max, asc, avg, round

spark = SparkSession.builder.appName("Disney Data Analysis").getOrCreate()
df = spark.read.csv("disney_plus_shows.csv", header=True, inferSchema=True)
df.select([count(when(col(c).isNull(), 1)) for c in df.columns]).show()
        </pre>
    </div>
</div>

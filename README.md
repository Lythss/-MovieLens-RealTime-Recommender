# MovieLens-RealTime-Recommender

## Description

This project aims to develop a real-time movie recommendation system using the MovieLens dataset. The system collects, processes, analyzes, and delivers personalized movie recommendations to users. It leverages several key technologies:

- **Apache Spark** for data preprocessing and transformation.
- **Elasticsearch** for fast indexing and search capabilities.
- **Kibana** for data visualization and analysis.
- **Flask** (or **FastAPI**) for building a REST API to interact with the system.

## Project Objectives

- **Data Collection:** Download and prepare the MovieLens dataset, which contains user interactions and movie metadata.
- **Data Preprocessing with Spark:** Clean and transform the data by handling missing values, converting data types, splitting the `genres` field into a list, and merging average ratings with movie information.
- **Recommendation Model:** Build and train a recommendation model (e.g., using Alternating Least Squares - ALS) to generate personalized recommendations.
- **Elasticsearch Integration:** Create indices and ingest the processed and modeled data for efficient search.
- **Kibana Visualization:** Set up dashboards to visualize:
  - Top 10 most popular movies.
  - Genre distribution.
  - User activity.
  - Average movie ratings, etc.
- **API Development:** Develop a REST API that:
  - Accepts a movie title as input.
  - Identifies users who interacted with that movie.
  - Uses their IDs to generate recommendations.
  - Returns the recommended movies from Elasticsearch.
- **GDPR Compliance and Data Governance:** Ensure the system complies with GDPR requirements by managing user consent and protecting personal data. Implement robust data governance policies to maintain data quality, security, and integrity.

## Technologies Used

- **Apache Spark** – For data processing and transformation.
- **Elasticsearch** – For data storage and search.
- **Kibana** – For data visualization.
- **Flask / FastAPI** – For creating the REST API.
- **MovieLens Dataset** – The data source for movie and user interaction information.

## Project Structure

graph TD
    A[MovieLens-RealTime-Recommender/] --> B[data/ # Raw and processed MovieLens dataset files]
    A --> C[spark/ # Spark scripts for data preprocessing and transformation]
    A --> D[model/ # Scripts for training and evaluating the recommendation model (e.g., ALS)]
    A --> E[elasticsearch/ # Scripts for integrating data into Elasticsearch]
    A --> F[kibana/ # Configuration files and dashboards for Kibana]
    A --> G[api/ # REST API code (Flask or FastAPI)]
    A --> H[docs/ # Additional documentation and guides]
    A --> I[README.md # This file]



## Installation and Setup

### Prerequisites

- [Java](https://www.java.com) (required for Apache Spark)
- [Python 3.x](https://www.python.org)
- [Apache Spark](https://spark.apache.org)
- [Elasticsearch](https://www.elastic.co/elasticsearch/)
- [Kibana](https://www.elastic.co/kibana/)
- [Flask](https://flask.palletsprojects.com/) or [FastAPI](https://fastapi.tiangolo.com/)

### Setup Instructions

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/your-username/MovieLens-RealTime-Recommender.git
   cd MovieLens-RealTime-Recommender
   ```

### Configure the Environment

Set up Apache Spark as per the official documentation.
Install and configure Elasticsearch and Kibana.
Update configuration files as needed.

### Data Preprocessing

Scripts in the spark/ directory will:

Load the MovieLens dataset.
Clean the data (handle missing values, convert data types).
Transform the genres field into a list.
Merge average ratings with movie metadata.

```bash
spark-submit spark/preprocessing.py --input data/movielens/raw --output data/movielens/processed
```
### Model Training

The recommendation model is trained using techniques like Alternating Least Squares (ALS).

### Features:

Load preprocessed data.
Train and evaluate the model.
Save the trained model for later use.


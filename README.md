# nyc-taxi-insights
# NYC Taxi Trip Insights

## Project Overview
This repository contains a comprehensive analysis of the NYC Taxi Trip Dataset as part of the Introduction to Big Data and Analytics course (Fall 2024) at George Washington University. The project leverages PySpark/Pandas for data processing and MLlib/scikit-learn for advanced analytics to extract meaningful insights from taxi trip data and develop predictive models for various taxi service metrics.

## Dataset Description
The NYC Taxi Trip Dataset contains detailed trip records from yellow taxis in New York City, dating back to 2009. Provided by the NYC Taxi and Limousine Commission (TLC), this dataset captures billions of taxi rides, making it one of the largest publicly available datasets for urban transportation research.

### Key Features
- **Pickup and Drop-off Timestamps**: When trips start and end
- **Pickup and Drop-off Locations**: Coordinates of trip origins and destinations
- **Trip Distance**: Distance traveled during trips (in miles)
- **Fare Amount**: Total cost including base fare, taxes, and surcharges
- **Payment Type**: Method of payment (cash or card)

### Data Collection Process
Each taxi is equipped with a GPS-enabled meter that records key details of every trip. The data is collected in real-time, stored in the TLC's central database, then anonymized and made available to the public for analysis.

## Analysis Focus
This project performs the following analyses and predictive modeling tasks:

1. **Demand Hotspot Identification**: Creating heatmaps of NYC showing taxi demand hotspots on weekly/monthly basis
2. **Trip Duration Prediction**: Predicting trip duration based on start time and location
3. **Passenger Segmentation**: Clustering passengers based on trip characteristics
4. **Payment Method Prediction**: Predicting whether passengers will pay by card or cash
5. **Borough-specific Fare Prediction**: Analyzing how fares vary across different NYC boroughs
6. **Tip Amount Prediction**: Forecasting tip amounts based on trip characteristics
7. **Fare Classification**: Predicting whether a trip will result in high or low fare
8. **Traffic Congestion Prediction**: Identifying congestion hotspots based on trip patterns

## Technical Implementation
- **Data Processing**: Apache Spark (PySpark) / Pandas
- **Machine Learning**: MLlib / scikit-learn
- **Development Environment**: Google Colab
- **Data Format**: Parquet (pre-formatted)
- **Visualization Libraries**: Matplotlib, Seaborn
- **Documentation**: Markdown within notebook

## Notebook Access
The complete analysis is available as a Google Colab notebook:
- [View and run the analysis notebook](https://colab.research.google.com/drive/1szHG2FYuOJvKCuD9qL2AwbKcAAjBzcS9?usp=sharing)

For the best experience with the interactive elements, open the notebook in Google Colab using the link above.

## Key Findings

### Demand Analysis
- Midtown Manhattan consistently shows the highest taxi demand, with peak hours between 4PM-7PM on weekdays
- Airport pickups (JFK and LaGuardia) display distinct patterns peaking at 8-10AM and 6-8PM
- Weekend demand hotspots shift notably toward entertainment districts with later evening peaks

### Trip Duration Models
- Achieved RMSE of 2.13 minutes using Gradient Boosting Regressor with temporal features
- Time of day accounts for 38% of trip duration variance, with pickup location contributing 27%
- Cross-borough trips show 35% higher duration variability than within-borough trips

### Passenger Segmentation
- Identified 4 distinct passenger clusters: Business Travelers (22%), Tourists (31%), Daily Commuters (35%), and Night Owls (12%)
- Payment methods strongly correlate with passenger segments - 87% of tourists prefer card payments
- Temporal features proved more effective for segmentation than geographical features

### Payment Prediction
- Random Forest classifier achieved 89.3% accuracy in predicting payment method
- Feature importance analysis shows trip distance, time of day, and pickup location as top predictors
- Passengers traveling to/from airports use cards 94% of the time, regardless of other factors

### Fare Analysis
- Borough-to-borough fare variations of up to 22% observed for similar distance trips
- Manhattan to Brooklyn trips command the highest per-mile fare premium (18% above average)
- XGBoost model achieved R² of 0.91 in predicting fares based on borough and temporal features

### Tipping Behavior
- Average tip percentage is 15.2%, with significant variation by pickup/dropoff location
- Airport trips receive 3.7% higher tips on average than non-airport trips
- Evening trips (6PM-10PM) receive 2.1% higher tips than morning trips
- Achieved RMSE of $0.87 in tip prediction using a stacked ensemble model

### Traffic Congestion
- Successfully identified 5 major congestion hotspots with >85% prediction accuracy
- Midtown tunnels and bridges show predictable congestion patterns with 92% accuracy
- Weather conditions improve congestion prediction models by 7.3% accuracy

## Future Work
- Incorporate weather data to improve prediction models
- Develop real-time prediction API for fare estimation
- Implement deep learning models for more accurate trip duration prediction
- Create interactive visualization dashboard for exploring patterns
- Expand analysis to include green taxis and ride-sharing services

## Setup Instructions
1. **Data Access**:
   - Access the TLC website to download the assigned 6 months of data
   - Upload the Parquet files to your Google Drive

2. **Environment Setup**:
   - Open the notebook in Google Colab
   - Mount your Google Drive to access the dataset
   - Ensure all required libraries are installed

## License
This project is for educational purposes only. The use of NYC TLC data is subject to their terms and conditions.

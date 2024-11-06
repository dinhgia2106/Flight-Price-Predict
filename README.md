# Flight Price Prediction Project

## Overview

This project collects, processes and analyzes flight data from different airports in Vietnam. It uses the Amadeus API to obtain flight information, processes the data and provides visualizations for insights into flight patterns, pricing and more. The processed data is then used to train a prediction model.

## Features

- Data collection from Amadeus API
- Data processing and cleaning
- Data visualization using matplotlib
- MySQL database integration
- Price prediction using Random Forest model

## System Requirements

- Python 3.x
- Required Python packages (install using `pip install -r requirements.txt`):
  - requests
  - pandas
  - matplotlib
  - mysql-connector-python
  - python-dotenv
  - tqdm
  - scikit-learn
  - seaborn

## Installation

1. Clone the repository
2. Install required packages: Run `pip install -r requirements.txt` in command line
3. Create `.env` file in root directory with following content:

```
API_KEY=your_amadeus_api_key
API_SECRET=your_amadeus_api_secret
DB_HOST=your_database_host
DB_USER=your_database_user
DB_PASSWORD=your_database_password
DB_NAME=your_database_name
DB_CLOUD_HOST=your_database_host
DB_CLOUD_USER=your_database_user
DB_CLOUD_PASSWORD=your_database_password
DB_CLOUD_NAME=your_database_name
```

4. Replace placeholder values in `.env` file with your actual credentials

## SQL Cloud Connection

1. Create SQL Cloud and connect with MySQL workbench, see tutorial [here](https://www.youtube.com/watch?v=_iOv1ec7tJQ)
2. Follow connection process similar to SQL.ipynb. You can also work directly on SQL Google Cloud, tutorial available [here](https://www.youtube.com/watch?v=jWkeFjfrCxQ)

## Usage

1. Run `data_collect.ipynb` to fetch flight data from Amadeus API
2. Run `data_visualization.ipynb` to create visualizations from collected data
3. Run `SQL_Cloud.ipynb` to process data and store in MySQL database
4. Run `model_training.ipynb` to train the Random Forest model for price prediction

## Project Structure

- `data_collect.ipynb`: Jupyter notebook for flight data collection
- `data_visualization.ipynb`: Jupyter notebook for data visualization
- `SQL_Cloud.ipynb`: Jupyter notebook for database operations
- `model_training.ipynb`: Jupyter notebook for training the Random Forest model
- `data/`: Directory containing CSV files with collected flight data
- `models/`: Directory containing trained model files
- `.env`: Configuration file for API keys and database credentials

## Data Source

- Amadeus API: Used to fetch real-time flight information

## Visualizations

The project includes various visualizations such as:

- Average flight prices by day
- Flight frequency by carrier
- Price distribution across different routes

## Database Structure

The project uses MySQL database with a `flights` table containing the following columns:

- id (Primary Key)
- departure_airport
- departure_time
- arrival_airport
- arrival_time
- carrier_code
- flight_number
- price
- duration

## Model Training

The project uses Random Forest Regression to predict flight prices based on various features:

- Features used for prediction:

  - Departure time
  - Arrival time
  - Flight duration
  - Carrier code
  - Route (departure and arrival airports)
  - Day of week
  - Season

- Model performance metrics:
  - R-squared score: Measures the proportion of variance in the dependent variable explained by the independent variables
  - Mean Absolute Error (MAE): Average absolute difference between predicted and actual prices
  - Root Mean Squared Error (RMSE): Square root of the average squared differences between predicted and actual prices

The model is trained on historical flight data and can be used to predict prices for future flights based on input features. The Random Forest algorithm was chosen for its ability to:

- Handle non-linear relationships
- Deal with both numerical and categorical features
- Provide feature importance rankings
- Resist overfitting through ensemble learning

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details

## Acknowledgments

- Amadeus API for providing flight data
- Contributors and maintainers of all used Python packages

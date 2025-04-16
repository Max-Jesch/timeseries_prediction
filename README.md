# Time Series Prediction with IBM Watson Machine Learning

This project demonstrates how to create, train, and deploy a time series prediction model using scikit-learn and IBM Watson Machine Learning (WML). The model predicts future values in a time series based on historical data.

## Features

- Synthetic time series data generation with customizable parameters
- Feature engineering with lagged values
- Linear regression model training and evaluation
- Model deployment to IBM Watson Machine Learning
- Real-time predictions using the deployed model
- Interactive visualizations of predictions

## Prerequisites

- Python 3.8+
- Jupyter Notebook
- IBM Cloud account with Watson Machine Learning service

## Installation

1. Clone this repository:
```bash
git clone https://github.com/yourusername/timeseries_prediction.git
cd timeseries_prediction
```

2. Create and activate a virtual environment:
```bash
python -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate
```

3. Install required packages:
```bash
pip install -r requirements.txt
```

## Project Structure

```
timeseries_prediction/
├── time_series_prediction.ipynb  # Main Jupyter notebook
├── requirements.txt              # Project dependencies
├── README.md                    # This file
└── .venv/                       # Virtual environment
```

## Usage

1. Open the Jupyter notebook:
```bash
jupyter notebook time_series_prediction.ipynb
```

2. Follow the notebook sections:
   - Import required libraries
   - Generate synthetic data
   - Prepare features and train model
   - Deploy model to WML
   - Test model on new data

3. To make predictions with the deployed model:
```python
scoring_payload = {
    "input_data": [{
        "values": [[lag_1, lag_2, lag_3]]  # Replace with your values
    }]
}
predictions = client.deployments.score(deployment_uid, scoring_payload)
```

## Configuration

Before running the notebook, update the following in the `deploy_to_wml` function:
- `wml_credentials`: Your IBM Cloud API key and URL
- `SPACE_ID`: Your WML deployment space ID

## Model Details

- **Model Type**: Linear Regression
- **Features**: 3 lagged values (lag_1, lag_2, lag_3)
- **Target**: Next value in the time series
- **Deployment**: Online deployment in IBM Watson Machine Learning

## Visualization

The notebook includes several visualizations:
- Training data plot
- Model performance on test data
- Predictions on new data

## Performance Metrics

The model's performance is evaluated using:
- Mean Squared Error (MSE)
- R-squared Score (R²)

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- IBM Watson Machine Learning
- scikit-learn
- pandas
- matplotlib 
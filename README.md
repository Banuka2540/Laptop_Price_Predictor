# Laptop Price Predictor

A machine learning-powered web application that predicts laptop prices based on specifications. The project uses a Random Forest Regressor model trained on laptop pricing data to provide price estimates in Sri Lankan Rupees (LKR).

## Features

- **Machine Learning Model**: Uses Random Forest Regressor with hyperparameter tuning for accurate predictions
- **Web Interface**: Clean, responsive Flask-based web application
- **Multiple Input Parameters**: Supports various laptop specifications including:
  - RAM (GB)
  - Weight (Kg)
  - Company/Brand
  - Laptop Type
  - Operating System
  - CPU Type
  - GPU Type
  - Touchscreen support
  - IPS display support

## Project Structure

```
Laptop_Price_Predictor/
├── laptop_price.csv          # Dataset with laptop specifications and prices
├── model.ipynb               # Jupyter notebook for data analysis and model training
├── predictor.pickle          # Trained machine learning model
├── website/
│   ├── app.py                # Flask web application
│   ├── model/
│   │   └── predictor.pickle  # Model file for the web app
│   ├── static/
│   │   └── styles.css        # CSS styling
│   └── templates/
│       └── main.html         # HTML template
└── README.md
```

## Dataset

The dataset contains 1,303 laptop entries with the following features:
- **Company**: Brand name (Apple, HP, Dell, Lenovo, Asus, Acer, MSI, Toshiba, etc.)
- **TypeName**: Laptop category (Notebook, Gaming, Ultrabook, 2-in-1 Convertible, Workstation, Netbook)
- **Inches**: Screen size
- **ScreenResolution**: Display resolution and panel type
- **CPU**: Processor specifications
- **RAM**: Memory size
- **GPU**: Graphics card
- **OpSys**: Operating system
- **Weight**: Laptop weight
- **Price_euros**: Price in Euros

## Machine Learning Pipeline

The model training process includes:

1. **Data Preprocessing**:
   - Converting RAM and Weight to numeric values
   - Extracting touchscreen and IPS panel features from screen resolution
   - Categorizing CPU, GPU, and operating system types
   - Grouping smaller company categories as "Other"

2. **Feature Engineering**:
   - One-hot encoding for categorical variables
   - 31 final features used for prediction

3. **Model Selection**:
   - Compared Linear Regression, Lasso, Decision Tree, and Random Forest
   - Random Forest Regressor selected with ~82% accuracy

4. **Hyperparameter Tuning**:
   - Grid Search CV with parameters: n_estimators, criterion

## Installation

### Prerequisites

- Python 3.8+
- pip

### Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/Banuka2540/Laptop_Price_Predictor.git
   cd Laptop_Price_Predictor
   ```

2. Install dependencies:
   ```bash
   pip install flask numpy pandas scikit-learn
   ```
   
   Or create a virtual environment first (recommended):
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   pip install flask numpy pandas scikit-learn
   ```

3. Run the web application:
   ```bash
   cd website
   python app.py
   ```

4. Open your browser and navigate to `http://localhost:5000`

## Usage

1. Enter the laptop specifications in the web form:
   - RAM size (in GB)
   - Weight (in Kg)
   - Select the company/brand
   - Choose the laptop type
   - Select the operating system
   - Choose CPU type
   - Select GPU type
   - Check touchscreen and IPS options if applicable

2. Click "Predict Price" to get the estimated price in LKR

## Technologies Used

- **Python**: Core programming language
- **Flask**: Web framework
- **scikit-learn**: Machine learning library
- **Pandas**: Data manipulation
- **NumPy**: Numerical computing
- **HTML/CSS**: Frontend interface

## Model Performance

| Model | Accuracy |
|-------|----------|
| Linear Regression | ~73% |
| Lasso | ~73% |
| Decision Tree | ~68% |
| **Random Forest** | **~82%** |

## License

This project is open source and available for educational purposes.

## Author

Banuka2540

## Contributing

Contributions are welcome! Feel free to submit issues or pull requests to improve the project.

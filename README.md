# Fix8 Web Application

Fix8 (Fixate) is an open source Python tool for visualizing and correcting eye tracking data. This project combines a desktop GUI application with a web interface for comprehensive eye tracking data analysis and correction.

## Project Overview

Fix8 supports manual, automated, and semi-automated correction methods for eye tracking data in reading tasks. The application provides tools for:

- Visualizing eye tracking data (fixations and saccades)
- Manual correction of fixation positions
- Automated correction algorithms
- Area of Interest (AOI) detection and analysis
- Data filtering and preprocessing
- Export capabilities for corrected data

## Project Structure

```
fix8-webapp/
├── app.py                          # Main Flask application entry point
├── requirements.txt                # Python dependencies
├── Procfile                       # Heroku deployment configuration
├── LICENSE                        # Project license
├── README.md                      # This file
│
├── website/                       # Web application package
│   ├── __init__.py               # Flask app factory
│   ├── views.py                  # Web routes and views
│   ├── math.py                   # Mathematical utilities
│   ├── templates/                # HTML templates
│   │   └── index.html           # Main web interface
│   ├── datasets/                 # Sample eye tracking datasets
│   │   ├── AlMadi2018/          # Research dataset
│   │   ├── Carr2022/            # Research dataset
│   │   ├── EMIP2021/            # Eye Movement in Programming dataset
│   │   ├── GazeBase/            # Gaze tracking dataset
│   │   ├── MET_Dataset/         # Multilingual eye tracking dataset
│   │   └── starter_examples/    # Basic examples
│   └── src/                      # Core Fix8 application source
│       ├── fix8.py              # Main Fix8 application class
│       ├── ui_main_window.py    # PyQt5 GUI interface
│       ├── state.py             # State management
│       ├── correction.py        # Correction algorithms
│       ├── driftAlgorithms.py   # Drift correction algorithms
│       ├── mini_emtk.py         # Eye movement toolkit utilities
│       ├── poly_editor.py       # Polygon editor for AOI
│       ├── canvas_resources.py  # Canvas drawing utilities
│       └── [dialog modules]     # Various dialog interfaces
│
└── test/                         # Testing framework
    ├── __init__.py
    ├── conftest.py              # Pytest configuration
    ├── run_tests.py             # Test runner
    ├── run_lint.py              # Linting runner
    ├── unit/                    # Unit tests
    │   └── test_math.py
    └── functional/              # Functional tests
        └── test_views.py
```

## Features

### Web Application (Flask)

- **Web Interface**: Browser-based access to Fix8 functionality
- **RESTful API**: Programmatic access to correction algorithms
- **Data Upload**: Upload eye tracking data files
- **Visualization**: Web-based data visualization
- **Export**: Download corrected data

### Supported Data Formats

- **JSON**: Native Fix8 format with fixations array
- **CSV**: Tabular format with x_cord, y_cord, duration columns
- **ASCII**: EyeLink 1000 ASCII format (with conversion)
- **Images**: PNG, JPG, JPEG stimulus images

## Installation and Setup

### Prerequisites

- Python 3.8 or higher
- pip (Python package installer)

### Local Development Setup

1. **Clone the repository**

   ```bash
   git clone <repository-url>
   cd fix8-webapp
   ```

2. **Create a virtual environment**

   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**

   ```bash
   pip install -r requirements.txt
   ```

4. **Set up environment variables**
   ```bash
   # Create a .env file in the project root
   echo "FLASK_SECRET_KEY=your-secret-key-here" > .env
   ```

### Running the Application

#### Web Application

```bash
python app.py
```

The web application will be available at `http://localhost:5000`

#### Desktop Application

```bash
python -m website.src.fix8
```

### Testing

Run the test suite:

```bash
python test/run_tests.py
```

Run linting:

```bash
python test/run_lint.py
```

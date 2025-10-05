# NASA Meteor Simulator Backend

A comprehensive backend system for simulating meteor impacts with real NASA data integration.

## Features

- **Impact Physics Engine**: Accurate calculations of crater formation, blast radius, and energy release
- **Damage Assessment**: Human casualties, infrastructure damage, and environmental impact modeling
- **NASA Data Integration**: Real-time data from NASA APIs and Earth observation systems
- **Machine Learning**: Enhanced predictions using historical impact data
- **Geographic Analysis**: Population density mapping and terrain effects
- **Multi-Planet Support**: Impact simulations on Earth for various asteroids
- **Gamified Mitigation Strategy System**: Implementation of mitigation strategies in a game-like simulation, with various strategies to implement, and a live global leaderboard

## NASA Data Sources

- **NASA Earthdata Search**: Atmospheric and surface data
- **NASA Open APIs**: Real-time astronomical data
- **GIBS/Worldview**: Earth observation layers
- **USGS EarthExplorer**: High-resolution terrain data
- **NOAA Open Data**: Atmospheric and oceanographic data
- **Planetary Data System (PDS)**: Planetary impact data

## Quick Start

**IMPORTANT: USE PYTHON 3.11**

1. Install dependencies:
```bash
pip install -r requirements.txt
```

2. Set up environment variables:
```bash
cp env.example .env
# Edit .env with your configuration; create .env.local for secrets
# Example for live NEO API:
# echo "NASA_API_KEY=YOUR_KEY" >> .env.local
```

3. Run the application:
```bash
uvicorn app.main:app --reload
```
Open another terminal in folder that contains index.html:
```bash
python -m http.server 8181
```
Go on:
localhost:8181/index.html


### Environment Variables

Key variables (see `env.example`):
- `NASA_API_KEY`: Required for live NASA NEO/EPIC APIs; optional in DEMO_MODE
- `DEMO_MODE`: If true, enables safe fallbacks and demo heuristics
- `CACHE_TTL_SECONDS`: In-memory cache TTL for NASA client
- `CORS_ALLOW_ORIGINS`: Comma-separated origins for CORS (e.g., http://localhost:3000)

### Using Your NASA API Key

Keep secrets out of version control:
```bash
cp env.example .env
echo "NASA_API_KEY=YOUR_KEY" >> .env.local
```

## Tech Stack

The project leverages a modern and robust tech stack to ensure high performance, scalability, and maintainability. Below is an overview of the technologies used:

### Core Framework
- **FastAPI**: A modern, fast (high-performance) web framework for building APIs with Python.
- **Uvicorn**: A lightning-fast ASGI server implementation for serving FastAPI applications.

### Scientific Computing
- **NumPy**: For numerical computations and array manipulations.
- **SciPy**: For advanced scientific and technical computing.
- **Pandas**: For data manipulation and analysis.
- **Scikit-learn**: For machine learning and data preprocessing.

### Database
- **SQLAlchemy**: A SQL toolkit and Object-Relational Mapping (ORM) library.
- **Alembic**: For database migrations.
- **PostgreSQL**: A powerful, open-source relational database.
- **Redis**: An in-memory data structure store used for caching and background tasks.

### Background Tasks
- **Celery**: A distributed task queue for handling asynchronous tasks.

### HTTP Clients
- **HTTPX**: For making asynchronous HTTP requests.
- **Aiohttp**: For asynchronous HTTP client/server handling.
- **Requests**: For synchronous HTTP requests.

### Geospatial Analysis
- **GeoPandas**: For working with geospatial data.
- **Shapely**: For geometric operations.
- **Rasterio**: For raster data processing.
- **Folium**: For creating interactive maps.

### Data Processing
- **Xarray**: For working with labeled multi-dimensional arrays.
- **NetCDF4**: For working with NetCDF data formats.
- **H5py**: For interacting with HDF5 data.

### Machine Learning
- **TensorFlow**: For deep learning and neural networks.
- **PyTorch**: For machine learning and deep learning tasks.
- **XGBoost**: For gradient boosting and decision tree-based models.

### Utilities
- **ReportLab**: For generating PDFs.
- **Matplotlib**: For data visualization.
- **Python-dotenv**: For managing environment variables.
- **Passlib**: For password hashing.
- **Email-validator**: For validating email addresses.

### Development Tools
- **Black**: For code formatting.
- **Isort**: For sorting imports.
- **Flake8**: For linting Python code.
- **Mypy**: For static type checking.

### Testing
- **Pytest**: For unit testing.
- **Pytest-asyncio**: For testing asynchronous code.

## Project Structure

```
app/
├── main.py                 # FastAPI application entry point
├── core/                   # Core configuration and utilities
├── models/                 # Pydantic data models
├── services/               # Business logic services
├── physics/                # Impact physics calculations
├── nasa/                   # NASA API integration
├── ml/                     # Machine learning models
├── database/               # Database models and connections
└── tests/                  # Test suite
```

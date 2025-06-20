# historical_options_pipeline

![Python Version](https://img.shields.io/badge/python-%3E%3D3.13-blue)

A high-performance pipeline for ingesting historical options data and exposing it via a FastAPI interface using PostgreSQL.

## Features
- Async ingestion with httpx
- PostgreSQL storage via SQLAlchemy
- Exposed APIs via FastAPI

## Overview
This project is a Python application that fetches historical options data from the Alpha Vantage API, processes it, and stores it in a PostgreSQL database.

It is designed to run as a background task, fetching data at regular intervals. 

The application is structured to be modular, with separate modules for fetching data, processing it, and storing it in the database.

It uses FastAPI for the web framework and SQLAlchemy for database interactions.

Example payload can be [viewed here.](https://www.alphavantage.co/query?function=HISTORICAL_OPTIONS&symbol=IBM&apikey=demo)


## 1. Create a .env file:

Create a `.env` file in the root directory of the project and add the following environment variables:


```shell
cp .env_example .env
nano .env
```


```plaintext
ALPHAVANTAGE_API_KEY=your_key
DATABASE_URL=postgresql+asyncpg://user:pass@localhost/dbname
```

## 2. Install dependencies:

```python
python --version
# Python 3.13.4

poetry install
```


## 3. Run the app:

```python
poetry run start
```



# SuperShop

SuperShop is a Django-based inventory management application built inside the `Django_project/` folder. It supports product, category, unit, inventory, and stock transaction management through a simple web interface and Django admin.

## Project Structure

- `Django_project/` - main Django project folder
  - `manage.py` - Django management script
  - `Django_project/` - project configuration module
    - `settings.py`
    - `urls.py`
    - `wsgi.py`
    - `asgi.py`
- `inventory/` - inventory application
  - `models.py` - Category, Unit, Product, Inventory, StockTransaction models
  - `views.py` - view functions for dashboard, products, inventory, transactions, categories, and units
  - `urls.py` - app URL routing
  - `admin.py` - admin registration
  - `templates/inventory/` - HTML templates
  - `tests.py` - placeholder for unit tests
- `db.sqlite3` - default SQLite database file
- `requirements.txt` - Python dependency list
- `runtime.txt` - runtime environment configuration

## Requirements

- Python 3.x
- Django 6.0.3
- `asgiref==3.11.1`
- `sqlparse==0.5.5`
- `tzdata==2025.3`

## Installation

1. Create and activate a virtual environment:
   ```bash
   python -m venv .venv
   .venv\Scripts\Activate.ps1
   ```
2. Install dependencies:
   ```bash
   pip install -r Django_project/requirements.txt
   ```
3. Run migrations:
   ```bash
   python Django_project/manage.py migrate
   ```
4. Create a superuser for admin access:
   ```bash
   python Django_project/manage.py createsuperuser
   ```

## Running the Application

Start the development server:

```bash
python Django_project/manage.py runserver
```

Open the application in your browser at:

- `http://127.0.0.1:8000/` - main dashboard
- `http://127.0.0.1:8000/admin/` - Django admin

## Features

- Dashboard showing total products, total stock, total transactions, and low-stock items
- Product management with categories and optional units
- Inventory list and stock summary
- Stock transaction entry with automatic inventory updates
- Category and unit management (list, add, edit, delete)
- Admin registration for core models

## Data Models

- `Category` - product categories
- `Unit` - measurement units with unique abbreviation
- `Product` - name, price, category, and unit
- `Inventory` - one inventory record per product
- `StockTransaction` - stock in / stock out with automatic inventory adjustment

## Notes

- `DEBUG` is enabled in `Django_project/Django_project/settings.py`; this should be disabled before production.
- The secret key is currently stored in source and should be moved to environment configuration for deployment.
- `inventory/tests.py` is present but contains no tests yet.

## Recommended Improvements

- Add Django forms or ModelForms for validation and cleaner form handling
- Add unit tests for inventory and transaction workflows
- Add authentication and permission checks for user access control
- Move secret key and configuration into environment variables
- Add static/media management and production deployment settings

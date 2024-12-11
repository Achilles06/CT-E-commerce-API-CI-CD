# CT-E-commerce-API-CI-CD

# CT-Factory API Documentation

## Overview
This project is a Flask-based API for managing e-commerce-like factory operations, including customers, products, orders, and employees. It is integrated with a PostgreSQL database and supports CI/CD pipelines using GitHub Actions.

---

## Features
- Modular API structure using Flask Blueprints.
- Database integration with PostgreSQL.
- CI/CD pipeline for automated testing and deployment to Render.
- Swagger integration for API documentation.
- Unit tests for core functionalities.

---

## Setup and Installation

### Prerequisites
- Python 3.9 or higher.
- PostgreSQL database.
- Git for version control.

### Installation Steps
1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd CT-FACTORY-API
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Configure the database:
   - Ensure the database connection URI in `app.py` matches your PostgreSQL setup.

4. Run database migrations:
   ```bash
   python app.py
   ```

5. Start the application:
   ```bash
   python app.py
   ```
   The API will be accessible at `http://127.0.0.1:5000`.

---

## Deployment on Render

1. Push the project to GitHub:
   ```bash
   git init
   git remote add origin <your-repository-url>
   git add .
   git commit -m "Initial commit"
   git push -u origin main
   ```

2. Create a new Web Service on Render and link your GitHub repository.

3. Set the **Start Command** to:
   ```bash
   gunicorn app:app
   ```

4. Add `DATABASE_URL` to the Render environment variables.

5. Deploy and monitor the service.

---

## CI/CD Pipeline

### GitHub Actions Workflow
The project includes a `.github/workflows/main.yml` file that:
- Runs on every push to the `main` branch.
- Installs dependencies and runs tests using `pytest`.
- Deploys the application to Render upon successful testing.

### Running Tests Locally
To run tests locally, use:
```bash
pytest
```

---

## API Documentation
Interactive Swagger API documentation is available at:
```plaintext
http://127.0.0.1:5000/apidocs
```

---

## Project Structure
```
CT-FACTORY-API
├── app.py                      # Main application file
├── blueprints                  # API blueprints
│   ├── customer.py             # Customer-related routes
│   ├── product.py              # Product-related routes
│   ├── order.py                # Order-related routes
├── config.py                   # Configuration file
├── models.py                   # Database models
├── requirements.txt            # Dependencies
├── .github/workflows/main.yml  # GitHub Actions workflow
├── static                      # Static files (Swagger YAML)
├── tests                       # Unit tests
└── README.md                   # Project documentation
```

---

## Contributing
Feel free to fork this repository and create pull requests for any features, bug fixes, or improvements.

---

## License
This project is licensed under the MIT License.

---

## Contact
For support, please reach out to [Your Contact Information].

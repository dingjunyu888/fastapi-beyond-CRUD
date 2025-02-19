# FastAPI Beyond CRUD 

This is the source code for the [FastAPI Beyond CRUD](https://youtube.com/playlist?list=PLEt8Tae2spYnHy378vMlPH--87cfeh33P&si=rl-08ktaRjcm2aIQ) course. The course focuses on FastAPI development concepts that go beyond the basic CRUD operations.

For more details, visit the project's [website](https://jod35.github.io/fastapi-beyond-crud-docs/site/).

## Table of Contents

1. [Getting Started](#getting-started)
2. [Prerequisites](#prerequisites)
3. [Project Setup](#project-setup)
4. [Running the Application](#running-the-application)
5. [Running Tests](#running-tests)
6. [Contributing](#contributing)

## Getting Started
Follow the instructions below to set up and run your FastAPI project.

### Prerequisites
Ensure you have the following installed:

- Python >= 3.10
- PostgreSQL
- Redis

### Project Setup
1. Clone the project repository:
    ```bash
    git clone https://github.com/jod35/fastapi-beyond-CRUD.git
    ```
   
2. Navigate to the project directory:
    ```bash
    cd fastapi-beyond-CRUD/
    ```

3. Create and activate a virtual environment:
    ```bash
    python3 -m venv env
    source env/bin/activate
    ```

4. Install the required dependencies:
    ```bash
    pip install -r requirements.txt
    ```

5. Set up environment variables by copying the example configuration:
    ```bash
    cp .env.example .env
    ```

6. Run database migrations to initialize the database schema:
    ```bash
    alembic upgrade head
    ```

7. Open a new terminal and ensure your virtual environment is active. Start the Celery worker (Linux/Unix shell):
    ```bash
    sh runworker.sh
    ```

## Running the Application
Start the application:

```bash
fastapi dev src/
```
Alternatively, you can run the application using Docker:
```bash
docker compose up -d
```
## Running Tests
Run the tests using this command
```bash
pytest
```

## Changes

### 1. Added GitHub Actions
- Added `commit-check.yml` and `nightly-build.yml` workflows.
- **Enforce Conventional Commits on PRs**: Ensures all pull requests follow the Conventional Commits specification.
- **Automate Nightly Builds**: Nightly builds are scheduled to run at 12 AM SF time (cron: `"0 8 * * *"`).
- **Failure Notifications**: Sends email notifications for PR and test failures.

### 2. Updated `compose.yml` and `Dockerfile`
- **Runs without extra downloads**: The application can be started with `docker compose up` without requiring additional downloads.
- **Automatically loads environment variables**: Environment variables are loaded seamlessly for Docker containers.

### 3. Modified `.env.example`
- Added required configuration for environment variables to ensure smooth setup.

### 4. Integrated Email Notifications
- **SendGrid Email**: Failure alerts are sent via SendGrid for PRs, test failures, and nightly build issues.


## Contributing
I welcome contributions to improve the documentation! You can contribute [here](https://github.com/jod35/fastapi-beyond-crud-docs).

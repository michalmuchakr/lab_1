---

# Team Management App

This project is a web application for managing team members, allowing users to add, view, and delete members with specific roles. The frontend is built with HTML, CSS, and JavaScript, while the backend uses Python and Flask. The application is Dockerized, with Nginx serving as the frontend server and a Flask server handling API requests.

## Table of Contents
- [Project Structure](#project-structure)
- [Features](#features)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [API Endpoints](#api-endpoints)
- [License](#license)

## Project Structure

```
project_root/
├── docker-compose.yml
├── nginx/
│   ├── Dockerfile
│   ├── config/
│   │   └── default.conf
│   └── ui_app/
│       ├── index.html
│       ├── logic.js
│       └── styles.css
├── python_server/
│   ├── Dockerfile
│   ├── app.py
│   └── requirements.txt
```

- **nginx/**: Contains the Dockerfile for Nginx, a custom configuration file (`default.conf`), and frontend files in `ui_app/`.
- **python_server/**: Contains the Dockerfile and Flask server files, including the main application file `app.py` and `requirements.txt`.

## Features

- Add team members with first name, last name, and role.
- Display a list of all team members.
- Delete team members based on a unique ID.
- Dockerized setup with multi-container orchestration for frontend and backend communication.

## Prerequisites

- [Docker](https://www.docker.com/get-started) and [Docker Compose](https://docs.docker.com/compose/install/)

## Installation

1. **Clone the Repository**:
   ```bash
   git clone <repository-url>
   cd lab_1
   ```

2. **Build and Start the Docker Containers**:
   ```bash
   docker-compose up --build
   ```

   This command builds the Docker images and starts the containers for Nginx (serving the frontend) and Flask (handling the backend).

3. **Access the Application**:
   - Open your browser and go to `http://localhost:8080`.

## Usage

1. **Add a Team Member**: Use the form on the main page to enter the first name, last name, and role for a new team member. Click "Submit" to add them to the team list.
2. **View Team Members**: All added team members are displayed in a list below the form.
3. **Delete a Team Member**: Click the trash icon next to a team member's entry to remove them from the list.

## API Endpoints

The backend provides the following API endpoints for managing team members:

- **GET /team**: Retrieve a list of all team members.
- **POST /team**: Add a new team member. Requires `firstName`, `lastName`, and `role` in the request body.
- **DELETE /team/<id>**: Remove a team member by their unique ID.

## Docker Configuration

This project uses Docker Compose for multi-container orchestration:

- **Nginx**: Serves the frontend application and proxies API requests to the Flask backend.
- **Flask (Python)**: Handles backend logic for managing team members. Configured to allow CORS for communication with the frontend.



---

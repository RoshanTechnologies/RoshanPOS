# GEMINI.md

## Project Overview

This project is **Open Source Point of Sale (OSPOS)**, a web-based point of sale system. It is a PHP application built on the **CodeIgniter 4** framework, with a frontend that uses **Bootstrap 3**, **jQuery**, and other JavaScript libraries. The backend uses **MySQL** or **MariaDB** for data storage.

The project is managed with both **Composer** for PHP dependencies and **npm** for frontend dependencies. It includes features like stock management, sales tracking, reporting, and more.

The directory `RoshanPOS` is a fork of the original `opensourcepos/opensourcepos` repository.

## Building and Running

### Docker (Recommended)

The easiest way to get the application running is by using Docker.

1.  **Start the services:**
    ```bash
    docker-compose up -d
    ```
    This will start the web server and database containers.

2.  **Access the application:**
    Once the containers are running, you can access the application in your web browser at `http://localhost`.

### Manual Build

If you are not using Docker, you will need to build the frontend assets and install the PHP dependencies manually.

1.  **Install PHP dependencies:**
    ```bash
    composer install
    ```

2.  **Install frontend dependencies:**
    ```bash
    npm install
    ```

3.  **Build frontend assets:**
    ```bash
    npm run build
    ```
    This will run the `gulp default` task, which compiles and minifies the CSS and JavaScript assets.

## Testing

The project uses **PHPUnit** for testing.

*   **Run all tests:**
    ```bash
    composer test
    ```

## Development Conventions

*   **Coding Style:** The project uses `php-cs-fixer` to enforce a consistent coding style for PHP code.
*   **Branching:** It is recommended to create feature branches for new development and to keep the `main` branch in sync with the upstream `opensourcepos/opensourcepos` repository.
*   **Frontend Build:** The frontend assets are managed with `gulp`. The main build task is `gulp default`, which can be run with `npm run build`.
*   **Database:** Database migrations are located in `app/Database/Migrations`. The base database schema is defined in `app/Database/tables.sql` and `app/Database/constraints.sql`, which are combined into `app/Database/database.sql` during the build process.

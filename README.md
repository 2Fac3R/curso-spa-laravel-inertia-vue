# notes-app
## Description

This project is a note-taking app, designed to exemplify a full-stack project, built with Laravel 8 on the backend and Vue.js + TailwindCSS on the frontend side. 
Thanks to the ease provided by Inertia.js, we can seamlessly connect both parts without much complexity.

Stack:

* PHP (7.3) + Laravel (8)
* Inertia.js: Build single-page apps, without building an API
* Vue.js: The Progressive JavaScript Framework
* HTML + CSS (TailwindCSS Framework)

## Installation

Clone the repository

    git clone https://github.com/2Fac3R/notes-app.git

Switch to the repo folder

    cd notes-app

Install all the dependencies using composer

    composer install

Rename ".env.example" to ".env" and add your database settings.
    
    DB_CONNECTION=mysql
    DB_HOST=127.0.0.1
    DB_PORT=3306
    DB_DATABASE=<your-database>
    DB_USERNAME=<your-username>
    DB_PASSWORD=<your-password>

Run migrations

    php artisan migrate

Run seeder, this will create one user and 30 notes

    php artisan db:seed

Start the local development server

    php artisan serve

## Usage
    
Get a list of notes

    http://127.0.0.1:8000/notes

Get a note by id

    http://127.0.0.1:8000/notes/{id}

Edit a note by id
    
    http://127.0.0.1:8000/notes/{id}/edit

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Any feedback is appreciated.

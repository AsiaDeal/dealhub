# ADH Project Setup Guide

This guide will walk you through the steps to set up a Laravel project on your local machine. Laravel is a popular PHP framework for building web applications.

## Prerequisites

Before you begin, make sure you have the following installed on your local machine:

- [PHP](https://www.php.net/)
- [Composer](https://getcomposer.org/)
- [Node.js](https://nodejs.org/)
- [npm](https://www.npmjs.com/) (comes with Node.js)
- [Git](https://git-scm.com/)

## Step 1: Clone the Repository

First, clone your Laravel project repository from a version control system like Git. Replace `<repository_url>` with your actual repository URL:
git clone <repository_url>

## Step 2: Install Composer Dependencies

Navigate to your project directory and install the PHP dependencies using Composer:

1. cd your-project-directory
2. composer install

## Step 3: Install NPM Dependencies

Next, install the JavaScript dependencies using npm:

npm install

## Step 4: Create a Copy of Your .env File

Create a copy of your .env.example file and rename it to .env:

cp .env.example .env

## Step 5: Generate an App Encryption Key

Laravel requires you to have an app encryption key which is generally randomly generated and stored in your .env file. The app will use this encryption key to encode various elements of your application from cookies to password hashes and more.

Laravel’s command-line tool called Artisan can take care of that. The key:generate command will generate a key and copy it to your .env file, ensuring that your user sessions and other encrypted data remain secure:

php artisan key:generate

If you check the .env file again, you will see that it now has a long random string of characters in the APP_KEY field. We now have a valid app encryption key.

## Step 6: Create an Empty Database for Your Application

Create an empty database for your project using the database tools you prefer (for example, phpMyAdmin).

## Step 7: Add Database Information to the .env File

In the .env file, add database information to allow Laravel to connect to the database. This information will vary depending on your database setup.

## Step 8: Migrate the Database

Once your credentials are in the .env file, now you can migrate your database. This creates the tables needed for the application to work.

php artisan migrate

## Step 9: Seed the Database (Optional)

You may also want to seed your database with dummy data for your application. This is entirely optional, but it’s a good idea if you want to have some fake data to work with as you build and test your application.

php artisan db:seed

## Step 10: Start Your Development Server

To start up your Laravel development server, go to your project directory in the terminal and run the following command:

php artisan serve

You can now access your Laravel application at http://localhost:8000.

## Step 11: You’re Done!

That’s it! You now have a Laravel project set up on your local machine. Happy coding!
Warehouse Management System (PHP)

A modular warehouse and production chain management system built with PHP, PDO, and a clean Front Controller architecture.
The system follows an MVC-inspired structure that keeps the application maintainable, extendable, and easy to scale.



 Project Structure

warehouse_system_php/
│
├── public/                         # Public environment (entry point + visible assets)
│   ├── index.php                   # Front Controller
│   ├── .htaccess                   # Redirect all requests to index.php
│   ├── js/                         # Bootstrap / Custom JS
│   └── css/                        # Stylesheets
│
├── app/                            # Application environment (business logic)
│   ├── Core/                       # Core system files
│   │   ├── Database.php            # Secure PDO connection
│   │   └── Router.php              # URL parsing and controller dispatching
│   │
│   ├── Models/                     # Database interaction layer
│   │   ├── BaseModel.php           # Base model (optional but useful)
│   │   ├── ProductModel.php        # Product handling
│   │   ├── InventoryModel.php      # Inventory operations
│   │   └── SalesModel.php          # Sales and invoice logic
│   │
│   ├── Controllers/                # Request handlers
│   │   ├── InventoryController.php
│   │   ├── SalesController.php
│   │   └── ProductionController.php
│   │
│   └── Config/                     # Application configuration
│       └── config.php              # DB name, username, password, host
│
├── resources/                      # View templates and resources
│   └── views/
│       ├── layouts/                # Layout templates (header/footer)
│       │   ├── header.php
│       │   └── footer.php
│       │
│       ├── dashboard.php           # Main dashboard
│       │
│       ├── inventory/              # Inventory views
│       │   ├── list.php
│       │   └── inbound_form.php
│       │
│       └── sales/                  # Sales views
│           └── invoice_form.php
│
├── vendor/                         # Composer dependencies (if using autoload)
│
└── README.md




 Features

Modular PHP structure with clear separation of concerns

Clean and simple URL routing

Secure PDO database interactions

Organized controllers and models

Bootstrap-ready UI structure

Easily extendable for new modules (HR, suppliers, accounting, etc.)

Compatible with Composer and PSR-4 autoloading



 Core Architecture

Front Controller

All HTTP requests go through a single file:

public/index.php

This improves security, routing, and prevents direct access to internal files.

Router

app/Core/Router.php handles:

URL parsing

Controller resolution

Method dispatching


Models

Reusable PHP classes that handle:

Database queries

CRUD operations

Business rules


Views

Located in resources/views/, organized by module:

Dashboard

Inventory

Sales


Views are pure HTML/PHP templates compatible with Bootstrap.



 Installation

1. Clone the repository

git clone https://github.com/<your-username>/<your-repo>.git

2. Configure your database

Update database credentials inside:

app/Config/config.php

3. Ensure .htaccess is enabled

Enable mod_rewrite in Apache, then confirm your .htaccess works:

public/.htaccess

4. Import the database

If a SQL file exists, import it into your MySQL server.

5. Run the project

Access:

http://localhost/warehouse_system_php/public




 Requirements

PHP 8.0+

MySQL / MariaDB

Apache server with mod_rewrite

Composer (optional but recommended)

Bootstrap 5 (front-end)



 Optional Composer Support

If you enable Composer autoloading:

composer init
composer dump-autoload

Then include it in public/index.php:

require_once "../vendor/autoload.php";




Future Enhancements (Roadmap)

User roles and permissions

REST API for mobile integration

Push notifications for stock alerts

Printable invoices with QR codes

Multi-language support

Reporting and analytics module



 License

MIT License — free to use, modify, and distribute.

# Warehouse-and-production-chain-management-system
The system efficiently manages warehouse and production tasks, recording all items in the warehouse, their quantities, and their locations, while also automatically calculating the missing quantity when producing each new item.

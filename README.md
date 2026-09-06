# Asp.Net-Core-Full-Stack-E-Commerce-Application



### 🛒 Enterprise Full-Stack E-Commerce Application

A comprehensive, production-ready E-Commerce platform built using **Asp.Net Core** and modern architecture patterns. This project demonstrates high proficiency in secure authentication, robust backend decoupling, and RESTful API engineering integrated with a dynamic frontend. 

### ⚡ Key Architectural & Technical Highlight

The application is engineered on top of advanced software architecture topics, ensuring high maintainability, loose coupling, and clean code principles: 

* **Generic Repository Pattern:** Abstracted database operations to eliminate code duplication and promote consistency across entities.
* **Unit of Work Design Pattern:** Managed business transactions securely, ensuring all database operations within a scope succeed or fail together (Atomicity).
* **Entity Framework Core (EF Core):** Utilized as the primary Object-Relational Mapper (ORM), writing highly optimized LINQ queries to manage data flows.
* **Fluent API:** Implemented for concrete and precise database schema configuration, separating entity models from database-specific configurations.
* **Fluent Validation:** Kept business models clean by separating validation rules into distinct, strong-typed validator classes.
* **Dependency Injection (DI):** Heavily utilized built-in IoC containers to ensure loose coupling and highly testable services.
* **Asp.Net Core Identity:** Configured for comprehensive user security, handling complex operations like User Registration, Secure Login, and "Forgot Password" token flows.
* **Data Transfer Objects (DTO):** Implemented to secure data transfer layers, preventing over-posting attacks and hiding sensitive data definitions from the frontend.

### 🛠️ System Components & Stack

### Backend & Web API Architecture

* **Framework:** Asp.Net Core (C#)
* **Database Language:** Standard SQL utilizing relational models
* **Database Engine:** Microsoft SQL Server (MSSQL)
* **API Operations:** Fully REST-compliant Web API handling standard GET, POST, PUT, and DELETE HTTP verbs.
* **CORS Management (Cross-Origin Resource Sharing):** Configured a custom CORS Policy within the Startup middleware configuration. This lifts cross-origin restrictions, safely exposing API endpoints to native browser scripting technologies.

### Frontend Environment

* **Technologies:** Semantic HTML5, Responsive CSS3, JavaScript (ES6+), jQuery.
* **Integration:** Interacts asynchronously with the Web API endpoints to provide smooth user experiences across product catalogs, search queries, and shopping categories.

### 📂 Project Architecture Overview

text

├── shopapp.webui      # Presentation Layer (MVC View / API Controllers, Startup Config)
├── shopapp.data       # Data Access Layer (EF Core Context, Migrations, Repositories)
├── shopapp.business   # Business Logic Layer (Services, Managers, Validations)
└── shopapp.entity     # Core Entities & Database Tables

Kodu dikkatli kullanın.

### 🚀 Getting Started & Configuration

### Prerequisites

* .NET SDK (Compatible with Core version)
* Microsoft SQL Server & SSMS (SQL Server Management Studio)

### 1. Database Connection String Configuration

To run the application locally, you must first establish a connection to your local database engine. 

1. Navigate to the web presentation layer: shopapp.webui
2. Open the appsettings.json file.
3. Locate the ConnectionStrings section and update the MsSqlDesktopConnection with your local SQL Server host and credentials:

json

"ConnectionStrings": {
    "MsSqlDesktopConnection": "Server=YOUR_SERVER_NAME;Database=ShopAppDB;Trusted_Connection=True;MultipleActiveResultSets=true"
}


*Note: This connection string is injected into the DI container inside the ConfigureServices method in Startup.cs.* 

### 2. Multi-Database Portability (e.g., MySQL Migration)

The current migration structure is configured specifically for **MSSQL**. If your local environment uses a different RDBMS (such as **MySQL**), follow these software engineering steps to update the infrastructure: 

1. Delete the existing Migrations folders located inside **both** shopapp.webui and shopapp.data layers.
2. Open the Package Manager Console or Terminal.
3. Generate a fresh database migration schema optimized for your new engine using the following command: 

bash

dotnet ef migrations add InitialCreate --project shopapp.data --startup-project shopapp.webui

4. Apply the schema updates directly to your newly configured database: 

bash

dotnet ef database update --project shopapp.webui


💡 *Architectural Note: This enterprise repository is fully decoupled and ready for architectural inspection during technical recruitment screenings.*




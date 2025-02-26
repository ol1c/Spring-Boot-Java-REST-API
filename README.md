# Spring Boot Java REST API

> A simple Spring Boot application that provides a RESTful API to manage data operations (CRUD) for a given resource.

## 📜 Project Overview

This project is a learning-focused implementation of a RESTful API using Spring Boot. It provides endpoints to perform CRUD (Create, Read, Update, Delete) operations on an item resource. The application uses PostgreSQL as the relational database and JdbcTemplate for database interactions.

This project is based on the [freeCodeCamp tutorial](https://www.freecodecamp.org/news/use-spring-boot-and-java-to-create-a-rest-api-tutorial/) and serves as a practical exercise in structuring and implementing a simple API.
## ⚙️ Technologies Used

- **Spring Boot** - A framework for building Java-based web applications.
- **Java 11+** - The version of Java used for building the project.
- **Maven** - Dependency management and build tool.
- **Spring Data JPA** - For interacting with the database.
- **PostgreSQL** - Relational database for storage during development.
- **Postman** - API testing tool used for testing the endpoints.

## 🔧 Installation

### Prerequisites

Before you begin, ensure you have the following tools installed on your local machine:

- **Java 11 or later**: You can download it from [AdoptOpenJDK](https://adoptopenjdk.net/).
- **Maven**: Follow the instructions on the [Maven website](https://maven.apache.org/download.cgi) for installation.
- **PostgreSQL**: Ensure you have PostgreSQL installed and running. You can download it from [PostgreSQL Official](https://www.postgresql.org/download/).

### Steps to Run Locally

1. **Clone the repository**:

```bash
git clone https://github.com/ol1c/Spring-Boot-Java-REST-API.git
cd Spring-Boot-Java-REST-API
```

2. **Set up the PostgreSQL database**:

   - Make sure PostgreSQL is running on your machine.
   - Create a new database, e.g., `expensetrackerdb`.
   - Update the database credentials in `src/main/resources/application.properties` as follows:

   ```properties
   spring.datasource.url=jdbc:postgresql://localhost:5432/expensetrackerdb
   spring.datasource.username=expensetracker
   spring.datasource.password=password
   ```

3. **Build the project** using Maven:

```bash
mvn clean install
```

4. **Run the application**:

```bash
mvn spring-boot:run
```

Your app will now be running at [http://localhost:8080](http://localhost:8080).

### Testing the API

You can use [Postman](https://www.postman.com/) to test the API endpoints. The following API calls are available:

## 🚀 API Endpoints

The application provides API endpoints to **track expenses**. For example the ability to manage **categories** resources:

### 1. **GET /api/categories**

- **Description**: Retrieves all categories from the database.
- **Response**: A list of all categories in JSON format.
- **Example Response**:

```json
[
  {
    "categoryId": 1,
    "userId": 1,
    "title": "Shopping",
    "description": "shopping expenses",
    "totalExpense": 500.0
  },
  {
    "categoryId": 2,
    "userId": 1,
    "title": "Subscriptions",
    "description": "all subscriptions expenses",
    "totalExpense": 30.0
  }
]
```

### 2. **GET /api/categories/{id}**

- **Description**: Retrieves a single category by its ID.
- **Example Request**: `GET /api/categories/1`
- **Example Response**:

```json
{
  "categoryId": 1,
  "userId": 1,
  "title": "Shopping",
  "description": "shopping expenses",
  "totalExpense": 500.0
}
```

### 3. **POST /api/categories**

- **Description**: Creates a new category in the database.
- **Example Request**:

```json
{
  "title": "Shopping",
  "description": "shopping expenses"
}
```

- **Example Response (created category)**:

```json
{
  "categoryId": 1,
  "userId": 1,
  "title": "Shopping",
  "description": "shopping expenses",
  "totalExpense": 0.0
}
```

### 4. **PUT /api/categories/{id}**

- **Description**: Updates an existing category.
- **Example Request**: `PUT /api/categories/1`

```json
{
  "title": "Shopping",
  "description": "updated description"
}
```

- **Example Response (updated category)**:

```json
{
  "categoryId": 1,
  "userId": 1,
  "title": "Shopping",
  "description": "updated description",
  "totalExpense": 0.0
}
```

### 5. **DELETE /api/categories/{id}**

- **Description**: Deletes a category by its ID.
- **Example Request**: `DELETE /api/categories/1`

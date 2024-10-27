# Connexus - Smart Contact Manager

Connexus is a Java-based smart contact management application designed to help users manage and organize contacts efficiently. It supports features like user sign-up, adding, removing, updating, and searching for contacts. This project leverages Java, Thymeleaf, SQL, JavaScript, and Tailwind CSS to deliver a smooth and responsive UI.

## Features

Connexus includes user authentication (sign-up and login), contact management features like adding, editing, and deleting contacts, and a responsive UI built with Tailwind CSS.

## Getting Started

Follow these steps to set up and run Connexus on your local machine.

### Prerequisites

Ensure you have the following installed: Java Development Kit (JDK) version 11 or later, Maven for dependency management, an SQL database (PostgreSQL or MySQL is recommended), and an IDE like IntelliJ, Eclipse, or VS Code with Java support. You’ll also need Git to clone the repository.

### Installation and Setup

1. **Clone the Repository**: Start by cloning the repository with `git clone https://github.com/your-username/connexus.git` and navigating into the project directory with `cd connexus`.

2. **Database Setup**: Create a new database (e.g., `connexus_db`) in your SQL database. Then, open the `application.properties` file located in the `src/main/resources` directory and update the database connection settings.

   ```properties
   spring.datasource.url=jdbc:postgresql://localhost:5432/connexus_db
   spring.datasource.username=your_db_username
   spring.datasource.password=your_db_password
   spring.jpa.hibernate.ddl-auto=update
Once you’ve configured the database, proceed to install the necessary dependencies. Open a terminal in the project directory and run `mvn clean install` to download and install all required packages using Maven. This will ensure that all dependencies are set up correctly for the project to function as intended.

After the dependencies are installed, you can start the application. Use your IDE’s run feature, or in the terminal, execute `mvn spring-boot:run`. This command will launch the application and make it accessible locally.

With the application running, open your web browser and go to `http://localhost:8080`. Here, you should see the Connexus login page, which confirms that the application is up and running. You can now sign up or log in, add contacts, and explore all the available features within the app.

If you encounter any issues, ensure that all configurations are correct and that the database server is running. Additional troubleshooting might involve checking the logs or verifying the database connection in the `application.properties` file.


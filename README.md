# Connexus - Smart Contact Manager

Connexus is a Java-based smart contact management application designed to help users manage and organize contacts efficiently. It supports features like user sign-up, adding, removing, updating, and searching for contacts. This project leverages Java, Thymeleaf, SQL, JavaScript, and Tailwind CSS to deliver a smooth and responsive UI.

## Features

Connexus includes user authentication (sign-up and login), contact management features like adding, editing, and deleting contacts, and a responsive UI built with Tailwind CSS.

## Project Structure

Connexus/
│
├── .mvn/                           # Maven wrapper files
├── src/                             # Source code directory
│   ├── main/                        # Main application code
│   │   ├── java/                    # Java source files
│   │   │   └── com/                 # Base package for the project
│   │   │       └── scm/             # Main application package
│   │   │           ├── config/      # Configuration classes (e.g., Spring config)
│   │   │           ├── controllers/ # Controller classes for handling requests
│   │   │           ├── entities/    # JPA entity classes (models)
│   │   │           ├── forms/       # Form/DTO classes for data transfer
│   │   │           ├── helpers/     # Helper/util classes
│   │   │           ├── repositories/ # Database repositories
│   │   │           ├── services/    # Service classes with business logic
│   │   │           └── Application.java  # Main Spring Boot application class
│   │   ├── resources/                # Resources for the application
│   │   │   ├── static/               # Static assets like images, CSS, JS
│   │   │   ├── templates/            # Thymeleaf templates (HTML files)
│   │   │   │   ├── user/            # Templates specific to user functionality
│   │   │   │   ├── about.html       # About page template
│   │   │   │   ├── base.html        # Base layout template
│   │   │   │   ├── contact.html     # Contact page template
│   │   │   │   ├── home.html        # Home page template
│   │   │   │   ├── index.html       # Index page template
│   │   │   │   ├── login.html       # Login page template
│   │   │   │   ├── message.html     # Message page template
│   │   │   │   ├── navbar.html      # Navbar layout template
│   │   │   │   ├── register.html    # Registration page template
│   │   │   │   └── services.html    # Services page template
│   │   │   └── application.properties # Spring Boot application configuration
├── target/                          # Build output (compiled code, JAR files)
├── .gitignore                       # Git ignore file
├── mvnw                             # Maven wrapper for Unix-based systems
├── mvnw.cmd                         # Maven wrapper for Windows
├── pom.xml                          # Maven project configuration (dependencies, plugins)
├── README.md                        # Project documentation
├── tailwind.config.js               # Tailwind CSS configuration
├── package-lock.json                # Front-end package lock file
└── package.json                     # Front-end project configuration


## Getting Started

Follow these steps to set up and run Connexus on your local machine.

### Prerequisites

Before you start, ensure you have the following installed:

- **Java** (JDK 11 or later)
- **Spring Boot** (via Spring Initializr or your existing Spring Boot project setup)
- **Windows** (for setting environment variables on Windows)
- **Google and GitHub Accounts**: You'll need to have accounts with both Google and GitHub to create OAuth credentials.
- **Spring Boot Project**: Clone or set up your Spring Boot project.

### Installation and Setup

1. **Clone the Repository**: Start by cloning the repository. Copy the link from the code option in the repository in github. Run the command : `git clone {the link you'll get}` and navigating into the project directory with `cd Review1`.

2. **Database Setup**: Create a new database (e.g., `connexus_db`) in your SQL database. Then, open the `application.properties` file located in the `src/main/resources` directory and update the database connection settings. The properties should look like this: 

   ```properties
   spring.datasource.url=jdbc:mysql://localhost:3306/{your db name}
   spring.datasource.username= {your username}
   spring.datasource.password= {your password}
   spring.jpa.show-sql=true
   spring.jpa.hibernate.ddl-auto=update
Change the localhost:port according the default port of your database. Once you’ve configured the database, proceed to install the necessary dependencies. Open a terminal in the project directory and run `mvn clean install` to download and install all required packages using Maven. This will ensure that all dependencies are set up correctly for the project to function as intended. Also run `npm install` to download the node dependencies.

If you have face any difficulty in any of the tailwind configuration, run this command in terminal: `npx tailwindcss -i ./src/main/resources/static/css/input.css -o ./src/main/resources/static/css/output.css --watch
`. 

---
## Creating Google OAuth Credentials

Follow these steps to create OAuth credentials for Google:

1. **Go to Google Cloud Console**:
   - Visit [Google Cloud Console](https://console.cloud.google.com/).
   
2. **Create a Project**:
   - Click on **"Select a Project"** or **"Create a New Project"**.
   - Name your project and click **"Create"**.

3. **Enable the Google API**:
   - In the left sidebar, go to **"APIs & Services" > "Library"**.
   - Search for **Google+ API** or any other relevant Google API (e.g., Gmail API) and click **"Enable"**.

4. **Create OAuth Credentials**:
   - In the left sidebar, go to **"APIs & Services" > "Credentials"**.
   - Click on **"Create Credentials"** and select **OAuth 2.0 Client IDs**.
   - Configure the consent screen by entering the required details (such as Application name, support email, etc.).
   - Choose **"Web application"** as the application type.
   - Under **Authorized redirect URIs**, enter the URI that your application will use (e.g., `http://localhost:8080/login/oauth2/code/google`).
   - Click **"Create"**.

5. **Get Your Client ID and Secret**:
   - After creating the credentials, you will be presented with your **Client ID** and **Client Secret**. Copy these values for later use.

---

## Creating GitHub OAuth Credentials

Follow these steps to create OAuth credentials for GitHub:

1. **Go to GitHub Developer Settings**:
   - Visit [GitHub Developer Settings](https://github.com/settings/developers).

2. **Create a New OAuth Application**:
   - Click on **"New OAuth App"**.

3. **Fill in the Application Details**:
   - **Application Name**: Enter a name for your application.
   - **Homepage URL**: Enter the URL for your project (e.g., `http://localhost:8080`).
   - **Authorization callback URL**: Enter the URL that GitHub should redirect to after authentication (e.g., `http://localhost:8080/login/oauth2/code/github`).
   
4. **Get Your Client ID and Secret**:
   - After creating the application, GitHub will display your **Client ID** and **Client Secret**. Copy these values for later use.

---

## Setting Up OAuth Credentials in Spring Boot

1. **Set Up Environment Variables on Your System**:
   Store your Google and GitHub OAuth credentials as environment variables on your system to keep them secure.

   ### For Google:
   - Open Command Prompt or PowerShell.
   - Run the following commands to set the credentials as environment variables:

     ```cmd
     setx GOOGLE_CLIENT_ID "your-google-client-id"
     setx GOOGLE_CLIENT_SECRET "your-google-client-secret"

     ```

   ### For GitHub:
   - Run the following commands to set the credentials as environment variables:

     ```cmd
     setx GITHUB_CLIENT_ID "your-github-client-id"
     setx GITHUB_CLIENT_SECRET "your-github-client-secret"
     ```

   > **Note**: Make sure to replace `"your-google-client-id"`, `"your-google-client-secret"`, `"your-github-client-id"`, and `"your-github-client-secret"` with the actual values you obtained from the Google and GitHub Developer consoles.

2. **Use the Environment Variables in `application.properties`**:
   In your `application.properties` or `application.yml`, reference the environment variables like this:

   ```properties
   # application.properties
   spring.security.oauth2.client.registration.google.client-id=${GOOGLE_CLIENT_ID}
   spring.security.oauth2.client.registration.google.client-secret=${GOOGLE_CLIENT_SECRET}

   spring.security.oauth2.client.registration.github.client-id=${GITHUB_CLIENT_ID}
   spring.security.oauth2.client.registration.github.client-secret=${GITHUB_CLIENT_SECRET}


After the dependencies are installed and OAuth credentials setup you can start the application. Use your IDE’s run feature, or in the terminal, execute `mvn spring-boot:run`. This command will launch the application and make it accessible locally.

With the application running, open your web browser and go to `http://localhost:8080/home`. Here, you should see the Connexus login page, which confirms that the application is up and running. You can explore all the available features within the app. Other pages are still being developed.

If you encounter any issues, ensure that all configurations are correct and that the database server is running. Additional troubleshooting might involve checking the logs or verifying the database connection in the `application.properties` file.


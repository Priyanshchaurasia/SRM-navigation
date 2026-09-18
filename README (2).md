# 🗺️ SRM Campus Navigator

A full-stack campus navigation web app for SRM University, built with **Spring Boot** and **HTML/CSS/JavaScript**. It features an interactive campus map, user login, a chatbot, and a persistent reviews system.

📄 For a detailed walkthrough, see [step-by-step-explaination.txt](step-by-step-explaination.txt).

---

## ✨ Features

- **Interactive campus map** to find buildings and locations across SRM
- **User login** with a pre-loaded admin account, plus a "Continue as Guest" option
- **Chatbot** page to help with navigation queries
- **Reviews system** where reviews are saved in a database and persist across server restarts
- **Built-in database console** to view and query stored data

## 🛠️ Tech Stack

| Layer    | Technology                          |
| -------- | ----------------------------------- |
| Backend  | Java 17+, Spring Boot, Spring Data JPA |
| Database | H2 (file-based, persistent)         |
| Frontend | HTML, CSS, JavaScript               |
| Build    | Apache Maven                        |

---

## 📁 Project Structure

```
SRM-navigation/
├── pom.xml                          # Maven build file
├── src/
│   └── main/
│       ├── java/com/srm/navigation/
│       │   ├── NavigationApplication.java   # Main class
│       │   ├── config/
│       │   │   └── DataInitializer.java     # Loads default user and locations
│       │   ├── controller/
│       │   │   └── ApiController.java       # Handles all API requests
│       │   ├── entity/
│       │   │   ├── Location.java            # Locations table
│       │   │   ├── Review.java              # Reviews table
│       │   │   └── User.java                # Users table
│       │   └── repository/
│       │       ├── LocationRepository.java
│       │       ├── ReviewRepository.java
│       │       └── UserRepository.java
│       └── resources/
│           ├── application.properties       # Database and server config
│           └── static/                      # Frontend files
│               ├── index.html               # Main map and login page
│               ├── chatbot.html
│               ├── reviews.html
│               └── style.css
└── srm-nav-db.mv.db                 # Database file (created after first run)
```

---

## ✅ Prerequisites

- **Java JDK 17** or newer
- **Apache Maven**

Check that both are installed and added to your PATH:

```bash
java -version
mvn -version
```

## 🚀 How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/Priyanshchaurasia/SRM-navigation.git
   cd SRM-navigation
   ```
2. Start the server:
   ```bash
   mvn spring-boot:run
   ```
3. Wait until you see a message like `Started NavigationApplication in X.XXX seconds`.
4. Open your browser at **http://localhost:8080**

---

## 📖 How to Use

| Page             | URL                                   |
| ---------------- | ------------------------------------- |
| Map and login    | http://localhost:8080                 |
| Chatbot          | http://localhost:8080/chatbot.html    |
| Reviews          | http://localhost:8080/reviews.html    |
| Database console | http://localhost:8080/h2-console      |

**Demo login credentials:**

- Email: `admin@srm.com`
- Password: `12345`

You can also click **Continue as Guest** to skip login.

### Viewing the database (optional)

Open http://localhost:8080/h2-console and use:

- **JDBC URL:** `jdbc:h2:file:./srm-nav-db`
- **Username:** `sa`
- **Password:** *(leave blank)*

Click **Connect** to browse the `USERS`, `LOCATIONS`, and `REVIEWS` tables and run SQL queries.

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).

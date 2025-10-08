# 🤝 Contributing to SinSo-API

Thank you for your interest in contributing to **SinSo-API** — the open-source Sinhala Song Lyrics API 🇱🇰!  
Your contributions help promote Sinhala music, culture, and open-source development.  

This guide will help you get started with contributing, reporting issues, or suggesting improvements.


## 🧭 Table of Contents
1. [How to Contribute](#how-to-contribute)
2. [Setting Up the Project](#setting-up-the-project)
3. [Database Setup](#database-setup)
4. [Branch, Commit & Comment Conventions](#branch-commit--comment-conventions)
5. [Ways to Contribute](#ways-to-contribute)
6. [Coding Guidelines](#coding-guidelines)
7. [Commit & PR Guidelines](#commit--pr-guidelines)
8. [Community Rules](#community-rules)
9. [Contact](#contact)


## 🚀 How to Contribute

Contributing is simple!  
1. **Fork** the repository  
2. **Create a branch** for your changes  
3. **Make your edits** (fix bugs, add features, write docs, etc.)  
4. **Commit and push** your branch  
5. **Open a Pull Request (PR)**  

Once reviewed, your contribution will be merged if it fits the project goals.  
We encourage all kinds of contributions — code, docs, ideas, testing, or even just feedback!

## ⚙️ Setting Up the Project

### 1. Clone your fork
```bash
git clone https://github.com/<your-username>/SinSo-API.git
cd SinSo-API
```

### 2. Open the project

Open the project in your preferred IDE (e.g., IntelliJ IDEA, VS Code, Eclipse).

### 3. Install dependencies

Make sure you have Java 17+ and Maven installed.

```bash
mvn clean install
```
## 🗄️ Database Setup

The main production database (SinSo.db) is encrypted using git-crypt for security reasons.
For development and testing, you can use the unencrypted sample database.
🔽 Steps to Set Up the Development Database

### 1. Download the development database
```bash
wget http://sinso-api.github.io/SinSo_Dev.db -O SinSo_Dev.db
```
Or manually download it from : http://sinso-api.github.io/SinSo_Dev.db

### 2. Move it into the correct directory
```bash
SinSo-API/src/main/resources/db/
```
Update your configuration
In src/main/resources/application.properties, change the database reference:
```bash
spring.datasource.url=jdbc:sqlite::resource:db/SinSo_Dev.db
```

### 3. Run the application
```bash
mvn spring-boot:run
```

You’re now ready to start developing with the sample database 🎵

### ⚠️ Important Notes Before Committing or Pushing

Before pushing your changes to GitHub:
1. Revert the application.properties file
2. Change the database path back to the original:
    ```bash
    spring.datasource.url=jdbc:sqlite:src/main/resources/db/SinSo.db
    ```

Do NOT stage or commit the sample/Dev database

Make sure the following file is not added to Git:
`src/main/resources/db/SinSo_Dev.db`

Check before committing:
- git status
- Never commit decrypted or development database files — they will be rejected during PR review.

### 🔐 Accessing the Encrypted Main Database (Optional for Core Contributors)

The main database (SinSo.db) is encrypted using git-crypt to protect original copyrighted song data.
If you’re a core contributor or require access to the real dataset:

1. Generate a new GPG key pair.
2. Send your public key file (publickey.asc) to:
📧 vishal@vishalrashmika.com
3. Send a small note of what you're planning to update in the database.

Once approved, your key will be added to the project’s git-crypt keyring, allowing you to decrypt secure files automatically.
## 🌿 Branch, Commit & Comment Conventions

To maintain a clean and consistent git history, we use the following conventions:
### 🪵 Branch Naming — Conventional Branch

- Create branches using the format specified in : https://conventional-branch.github.io/


### 🧱 Commit Messages — Conventional Commits
- Create commits using the format specified in : https://www.conventionalcommits.org/en/v1.0.0/

### 💬 Code Review Comments and issues — Conventional issues & Comments
- Create issues and code reviews using the format specified in : https://conventionalcomments.org/


## 💡 Ways to Contribute
- Add new features or API endpoints
- Improve documentation or README files
- Report bugs or suggest enhancements
- Help with testing and performance improvements
- Create examples or tutorials using the API

## 🧱 Coding Guidelines
- Follow Java naming conventions and Spring Boot best practices
- Keep your code clean, modular, and well-documented
- Use meaningful commit messages
- Avoid hardcoding secrets or credentials
- Add comments or Javadoc for public methods

## 🤝 Community Rules
- Be respectful and supportive of others
- Avoid spam or irrelevant content
- Follow open-source ethics and licensing
- Credit original authors where applicable

## 📬 Contact
For questions, suggestions, or to request git-crypt access:
📧 vishal@vishalrashmika.com
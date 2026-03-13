# Startup Collaboration and Innovation Platform

A comprehensive Web Forms application designed to foster collaboration and innovation by bringing together Startups, Investors, Students, and Administrators.

## 🚀 Features Highlights

The platform caters to four distinct user roles, each with dedicated functionalities:

### 1. 🏢 Startup
- **Upload Project Idea:** Detail and share innovative project concepts.
- **Add Requirements:** Specify resources, talent (students), or funding needed.
- **Show Investor Interest:** Track and respond to investors interested in funding.
- **Show Student Interest:** Manage students wishing to collaborate or gain experience.

### 2. 💰 Investor (Invester)
- **View Startups:** Browse through registered startups and their ideas.
- **Recommendations:** Get automated or curated startup recommendations.
- **Project Information (`info_project`):** View detailed statistics and information about a startup's progress and needs.

### 3. 🎓 Student (User)
- **View Posts:** Access and browse posts and requirements published by startups.
- **Show Interest:** Demonstrate intent to collaborate or intern with startups.
- **Project Information (`info_project`):** Find out in-depth details about startup ideas.
- **Resume Uploading:** Submit resumes for startup matching and collaboration.

### 4. ⚙️ Admin
- Platform and system administration functionalities.

## 🛠️ Technology Stack

- **Frontend:** HTML, CSS (`style.css`), JavaScript (`bundle.js`).
- **Backend:** ASP.NET Web Forms (C# `4.5` framework).
- **Database:** Microsoft SQL Server.
- **Configuration Engine:** Web.config managing database connection strings and system settings.

## 📋 Database Configuration

The application expects a SQL database named `startup`.

**Setup Process:**
1. Connect to Microsoft SQL Server Data Engine.
2. Execute the `startup_data.sql` script to structure all application tables (such as `Registration`).
3. If necessary, refer to `startup.txt` which contains snippets of database schema scripts.
4. Open the `Web.config` in the root folder and verify the connection string:
   ```xml
   <add name="StarupConnectionString" connectionString="Data Source=YOUR_SERVER_NAME;Initial Catalog=startup;Integrated Security=True" providerName="System.Data.SqlClient"/>
   <add key="LIS" value="Data Source=YOUR_SERVER_NAME;Initial Catalog=startup;Integrated Security=True"/>
   ```

## 💻 Getting Started

1. Set up the Database as mentioned above.
2. Open `Startup Collaboration and Innovation Platform.sln` inside Visual Studio.
3. Keep the Startup Project pointing to the root and build the solution (Ctrl+Shift+B).
4. Run the project in a browser (typically landing at `home.aspx` or `Sign_in.aspx`).

## 📁 Directory Structure Overview

- `Admin/` - Administrative control panels and master pages.
- `Invester/` - Investor portal files, profiles, views, and dashboards.
- `Startup/` - Startup-specific features such as requirements, idea uploads, and interest gauges.
- `user/` - Student (general user) pages to browse projects and apply.
- `css/`, `images/`, `js/` - Public assets and theme scripts.
- `*Registration.aspx` - Registration forms based on roles.

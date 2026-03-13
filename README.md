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

The application expects a SQL database named `startup`. Since the database files (`startup_data.sql` and `startup.txt`) and configuration (`Web.config`) have been excluded from this repository for security, you will need to set them up manually.

**Setting up the Database:**
1. Open Microsoft SQL Server Management Studio (SSMS).
2. Create a new database named `startup`.
3. Create the required tables. For example, the `Registration` table needs the following schema:
   ```sql
   CREATE TABLE [dbo].[Registration](
       [u_id] [int] IDENTITY(1,1) NOT NULL,
       [fname] [nvarchar](max) NULL,
       [email] [nvarchar](max) NULL,
       [password] [nvarchar](50) NULL
   ) ON [PRIMARY] TEXTIMAGE_ON [PRIMARY]
   ```
   *(Note: You will also need to create tables for startups, investors, students, and required projects based on the model in the Web Forms pages.)*

**Setting up `Web.config`:**
1. Create a file named `Web.config` in the root folder of the project.
2. Add the following base configuration and update the `Data Source` with your local SQL Server instance name:
   ```xml
   <?xml version="1.0"?>
   <configuration>
     <connectionStrings>
       <add name="StarupConnectionString" connectionString="Data Source=YOUR_SERVER_NAME;Initial Catalog=startup;Integrated Security=True" providerName="System.Data.SqlClient"/>
     </connectionStrings>
     <system.web>
       <compilation debug="true" targetFramework="4.5">
         <assemblies>
           <add assembly="System.Management, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B03F5F7F11D50A3A"/>
         </assemblies>
       </compilation>
       <pages controlRenderingCompatibilityVersion="4.0"/>
     </system.web>
     <appSettings>
       <add key="LIS" value="Data Source=YOUR_SERVER_NAME;Initial Catalog=startup;Integrated Security=True"/>
     </appSettings>
   </configuration>
   ```

## 💻 Getting Started

1. Set up the Database as mentioned above.
2. Open `Startup Collaboration and Innovation Platform.sln` inside Visual Studio.
3. Keep the Startup Project pointing to the root and build the solution.
4. Run the project in a browser (typically landing at `home.aspx` or `Sign_in.aspx`).

## 📁 Directory Structure Overview

- `Admin/` - Administrative control panels and master pages.
- `Invester/` - Investor portal files, profiles, views, and dashboards.
- `Startup/` - Startup-specific features such as requirements, idea uploads, and interest gauges.
- `user/` - Student (general user) pages to browse projects and apply.
- `css/`, `images/`, `js/` - Public assets and theme scripts.
- `*Registration.aspx` - Registration forms based on roles.

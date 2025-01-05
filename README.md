# Job Application Tracker

## Overview

The **Job Application Tracker** is a web application designed to help users manage their job applications efficiently. It provides a centralized platform where users can keep track of all their applications, monitor the progress of each application, and analyze various statistics related to their job search process. The application features an intuitive dashboard for managing applications and a statistics page to visualize application metrics, providing users with insights into their job application activities.

### Why I Built This Application

Although most job sites provide features to track applications, I wanted to build a custom solution to have all my job applications in one centralized location, regardless of the platform I applied through. This web application allows me to easily monitor the status of my applications, add notes, and track the companies I've applied to. Additionally, by analyzing trends, I can gain insights into my application habits and optimize my job search.

## Features

- **Application Dashboard**: View, add, edit, and delete job applications from various platforms.
- **Application Status Tracking**: Easily update the current status of your job applications (e.g., Interview, Rejected, Offer).
- **Statistics Page**: Visualize your job application data, including metrics such as average applications per month, total companies applied to, and more.
- **Charts**: Display various statistics with visually appealing charts to help you analyze your progress.
- **Responsive Design**: Optimized for both desktop and mobile devices.
- **Dark Mode**: Toggle between light and dark themes for a comfortable user experience.

## Technology Stack

- **Frontend**:
  - **React**: JavaScript library for building user interfaces.
  - **TypeScript**: A typed superset of JavaScript that enhances code quality and maintainability.
  - **Tailwind CSS**: A utility-first CSS framework for rapidly building custom designs.
  - **Chart.js**: A JavaScript charting library for displaying various job application statistics.
  - **React Router**: For routing between different pages in the app.

- **Backend**:
  - **C# with ASP.NET Core**: Backend framework for building a RESTful API and managing the application's logic.
  - **SQL Server**: A relational database for storing user and application data.
  - **Entity Framework Core**: ORM for managing the database interactions with C#.

## Database Schema

The application stores and processes data related to job applications and user information in SQL Server. Below is an explanation of the key tables and their structure.

### Users Table

| Column Name              | Data Type           | Description |
|--------------------------|---------------------|-------------|
| **SecurityStamp**         | `nvarchar`          | A unique stamp for security purposes to handle changes in the user's account. |
| **ConcurrencyStamp**      | `nvarchar`          | A token used to track changes to the user’s record. |
| **PhoneNumber**           | `nvarchar`          | The user's phone number. |
| **PhoneNumberConfirmed**  | `bit`               | Indicates if the user's phone number is confirmed. |
| **TwoFactorEnabled**      | `bit`               | Indicates whether two-factor authentication is enabled. |
| **LockoutEnd**            | `datetimeoffset`    | The end time of a user's account lockout if applicable. |
| **LockoutEnabled**        | `bit`               | Indicates whether account lockout is enabled. |
| **AccessFailedCount**     | `int`               | The number of failed login attempts. |

### Applications Table

| Column Name              | Data Type           | Description |
|--------------------------|---------------------|-------------|
| **Id**                   | `uniqueidentifier`  | A unique identifier for each job application. |
| **Company**              | `nvarchar`          | The name of the company where the application was submitted. |
| **Position**             | `nvarchar`          | The job position being applied for. |
| **Location**             | `nvarchar`          | The location of the job (city, region, or remote). |
| **Link**                 | `nvarchar`          | A URL link to the job posting or application page. |
| **Date**                 | `datetime2`         | The date the application was submitted. |
| **Status**               | `nvarchar`          | The current status of the application (e.g., Applied, Interviewing, Rejected, Offer). |
| **UserId**               | `uniqueidentifier`  | A foreign key linking the application to a specific user. |

### Example Data

Here’s an example of what a record in the **Applications** table might look like:

| Id (Guid)                | Company             | Position            | Location      | Link                           | Date       | Status     | UserId (Guid)          |
|--------------------------|---------------------|---------------------|---------------|--------------------------------|------------|------------|------------------------|
| 1f63c2d8-9fdb-4130-8c6c-2a9f4a768039 | Tech Corp           | Software Engineer   | Bucharest     | https://example.com/apply      | 2024-12-10 | Applied    | 123e4567-e89b-12d3-a456-426614174000 |
| 2c54b9a2-a95f-4c44-b98b-82fbbf85e123 | Innovate Ltd.       | Data Analyst        | Remote        | https://example.com/apply      | 2024-12-15 | Interview  | 123e4567-e89b-12d3-a456-426614174000 |

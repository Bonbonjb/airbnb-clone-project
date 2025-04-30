# Airbnb Clone Project

##  Overview
This project is a backend implementation of an Airbnb-like application. The goal is to replicate the core functionality of Airbnb — including user registration, property listings, bookings, payments, and reviews — using modern web development technologies. The backend is designed to be scalable, efficient, and secure.

##  Project Goals
* Build secure user authentication and profile management.
* Enable creation, retrieval, and management of property listings.
* Implement a full-featured booking system.
* Integrate payment processing for secure transactions.
* Allow users to post and manage reviews for properties.
* Optimize data access and storage for performance and scalability.

##  Technology Stack
* **Django** – High-level Python web framework for developing RESTful APIs.
* **Django REST Framework** – Extension to Django for building Web APIs.
* **PostgreSQL** – Robust relational database for structured data storage.
* **GraphQL** – Flexible query language for interacting with APIs.
* **Celery** – Handles asynchronous tasks like sending emails or notifications.
* **Redis** – In-memory store used for caching and session management.
* **Docker** git add README.md
* **CI/CD Pipelines** – Automate testing, building, and deployment (e.g., GitHub Actions).

##  Team Roles

### *Product Owner (PO)*
* **Responsibilities:**
  * Defines the product vision and strategy.
  * Manages the product backlog and prioritizes features.
  * Ensures the final product meets customer requirements.
  * Acts as the primary liaison between stakeholders and the development team.

### *Business Analyst (BA)*
* **Responsibilities:**
  * Understands and analyzes business processes and requirements.
  * Translates business needs into technical specifications.
  * Facilitates communication between stakeholders and the development team.
  * Ensures that the development aligns with business objectives.

### *Project Manager (PM)*
* **Responsibilities:**
  * Plans, executes, and closes projects according to deadlines and budgets.
  * Coordinates team activities and resources.
  * Manages risks and resolves issues that arise during development.
  * Communicates project status to stakeholders.

### *UI/UX Designer*
* **Responsibilities:**
  * Designs user interfaces that are intuitive and user-friendly.
  * Enhances user experience through research and testing.
  * Creates wireframes, prototypes, and design specifications.
  * Collaborates with developers to implement designs effectively.

### *Software Architect*
* **Responsibilities:**
  * Designs the overall system architecture and selects appropriate technologies.
  * Ensures scalability, security, and performance of the application.
  * Guides the development team on architectural best practices.
  * Reviews code and design decisions to maintain architectural integrity.

### *Backend Developer*
* **Responsibilities:**
  * Implements server-side logic, databases, and APIs.
  * Ensures data integrity and security.
  * Integrates third-party services and APIs.
  * Collaborates with frontend developers to deliver cohesive functionality.

### *Frontend Developer*
* **Responsibilities:**
  * Develops client-side applications using modern frameworks.
  * Implements responsive and interactive user interfaces.
  * Integrates frontend with backend services.
  * Ensures cross-browser compatibility and performance optimization.

### *Quality Assurance (QA) Engineer*
* **Responsibilities:**
  * Develops and executes test plans to ensure software quality.
  * Identifies, documents, and tracks bugs.
  * Performs regression, performance, and security testing.
  * Collaborates with developers to resolve issues and improve product quality.

### *DevOps Engineer*
* **Responsibilities:**
  * Automates deployment processes and manages CI/CD pipelines.
  * Monitors system performance and ensures uptime.
  * Manages infrastructure and configuration.
  * Implements security measures and compliance standards.

##  Technology stack

 This project employs a current web development stack to create a scalable, maintainable, and durable platform.


### *Django* 
* Django is a high-level Python web framework used for application backend development.  
* It enables rapid development, has a clean architecture, and contains an ORM for database interaction.

### *Django REST Framework (DRF)*
* Is a powerful and flexible toolkit built on top of Django for building Web APIs.
* Simplifies the process of building and consuming APIs.

### *PostgreSQL* 
* A robust open-source relational database system. 
* Used to store and manage structured data such as user profiles, bookings, and property information.

### *GraphQL*
* This is a query language for APIs that enables customers to request specific data. 
* In comparison to REST APIs, it allows for more efficient data fetching and reduces over-fetching.

### *Celery*
* A distributed task queue for handling asynchronous operations.
* Manages background tasks such as sending emails, processing payments, and generating reports.

### *Redis*
* An in-memory data store used as a database, cache, and message broker.
* Supports fast access to frequently used data and helps with task queue management (via Celery).

### *Docker*
* This is a containerization platform packages and deploys applications in isolated environments. 
*  Maintains consistency across the development, testing, and production environments.


### *CI/CD Pipelines (e.g., GitHub Actions)*
* This CI/CD solution integrates with GitHub to automate testing, building and deployment operations.  
* Ensures code quality and reduces manual errors through continuous integration and delivery workflows.


##  Database Design

### 1. **Users**
- `id`: Primary key
- `username`: Unique name for login
- `email`: User email (unique)
- `password_hash`: Encrypted password
- `role`: ‘guest’ or ‘host’

### 2. **Properties**
- `id`: Primary key
- `user_id`: Foreign key referencing Users (host)
- `title`: Property name
- `description`: Property details
- `price_per_night`: Rental price

### 3. **Bookings**
- `id`: Primary key
- `user_id`: Foreign key referencing Users (guest)
- `property_id`: Foreign key referencing Properties
- `start_date`: Booking start date
- `end_date`: Booking end date

### 4. **Reviews**
- `id`: Primary key
- `user_id`: Foreign key referencing Users
- `property_id`: Foreign key referencing Properties
- `rating`: Numerical score (1–5)
- `comment`: Review text

### 5. **Payments**
- `id`: Primary key
- `booking_id`: Foreign key referencing Bookings
- `amount`: Total amount paid
- `payment_date`: Timestamp of transaction
- `status`: Completed, Pending, Failed

### **Entity Relationships**
- A **User** can own multiple **Properties** (1:M)
- A **User** can make multiple **Bookings** (1:M)
- A **Booking** belongs to one **User** and one **Property** (M:1)
- A **Property** can have multiple **Reviews** (1:M)
- A **Booking** has one **Payment** (1:1)


## Feature Breakdown

### 1. User Management
The User Management system is responsible for handling user registration, authentication, and profile management. It allows users to securely create accounts, log in, and update their personal information, ensuring that each user can manage their profile effectively and securely.

### 2. Property Management
The Property Management feature enables hosts to list, update, and delete their properties. This allows users to create property listings with essential details such as location, price, and description, facilitating the booking process for potential customers.

### 3. Booking System
The Booking System allows users to make and manage bookings for properties. This system tracks reservation details, including check-in and check-out dates, guest information, and property availability, ensuring a smooth booking experience for both users and hosts.

### 4. Payment Processing
The Payment Processing feature integrates a secure payment system to handle transactions for bookings. This ensures that users can pay for their reservations, and hosts receive their earnings while maintaining a safe and seamless financial flow.

### 5. Review System
The Review System allows users to post and manage reviews for properties they have stayed in. This helps build trust within the community by allowing customers to rate properties and share their experiences, guiding future guests in their booking decisions.

### 6. Data Optimization
Data Optimization ensures that the platform operates efficiently by optimizing data retrieval and storage. Techniques like database indexing and caching strategies are used to improve performance, especially when dealing with a large volume of users, properties, and bookings.


## API Security

### Authentication.
Authentication guarantees that only verified users have access to specific areas of the program/application.  It demands users to verify their identity, which is usually done through username/password combinations or authentication tokens.  In our project, we will employ token-based authentication (JWT) to safely validate users.  This is critical for safeguarding sensitive information such as user data, bookings, and payment details.

### Authorization.
Authorization determines what authenticated users are permitted to execute.  Following authentication, we utilize authorization to grant certain roles and permissions to users (for example, a regular user can book a property but only a host can manage their own properties).  This ensures that users can only take actions that are permitted, preventing unauthorized access to sensitive resources.

### Rate Limiting.
Rate limitation eliminates misuse by limiting the amount of requests a user can make to the API in a given time period.  This helps safeguard the backend from denial-of-service attacks and ensures that the application performs well even under high demand.  It is crucial for ensuring service availability and keeping malicious users from overwhelming the system.

### Encryption.
Encryption protects sensitive data, such as user passwords and payment information, both during transmission (via HTTPS) and when kept in the database.  This stops unauthorized individuals from accessing or manipulating sensitive data.

### Input Validation.
Input validation helps prevent harmful inputs, such as SQL injection or cross-site scripting (XSS), by verifying that all incoming data follows the required format.  It is critical for securing the system and preventing users from malicious behaviors that could jeopardize the platform's stability.

### Data Privacy.
Data privacy measures will be adopted to ensure that user information, such as personally identifiable information (PII) and payment information, is handled securely.  By following data protection standards (such as GDPR), we can ensure that users' privacy is respected and their data is protected from unauthorized access.


 

  

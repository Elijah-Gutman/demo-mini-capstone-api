# Blogging Platform Backend

## Overview

This project is a fully functional backend for a blogging platform built with **Ruby on Rails**. It demonstrates expertise in setting up and managing **relational databases**, implementing secure **user authentication**, and ensuring that all responses are seamlessly integrated with the frontend. The platform allows users to register, log in, and create posts, showcasing a developer's ability to handle the full lifecycle of backend development.

---

## Features

### 1. Relational Database Setup

- Designed and implemented a **relational database schema** using ActiveRecord and PostgreSQL.
- Established a **one-to-many relationship** between `users` and `posts`:

  - Each user can create multiple posts (`user_id` foreign key in the `posts` table).
  - Example:

    ```ruby
    class User < ApplicationRecord
      has_many :posts
    end

    class Post < ApplicationRecord
      belongs_to :user
    end
    ```

- Ensured database integrity with appropriate migrations, validations, and indexing for efficient queries.

### 2. User Authentication

- Implemented secure **login and signup functionality** using Rails’ `has_secure_password` and `bcrypt`:
  - Passwords are securely hashed and stored in the `users` table.
  - Users can log in with their email and password to create, edit, and delete their posts.
- Built middleware to authenticate users before granting access to restricted resources:

  ```ruby
  before_action :authenticate_user

  private

  def authenticate_user
    render json: { error: "Unauthorized" }, status: :unauthorized unless current_user
  end
  ```

3. API Endpoints
   Developed robust and RESTful API endpoints to handle CRUD operations for users and posts:
   Users API:
   POST /users to create a new user.
   POST /sessions to handle user login and generate secure tokens.
   Posts API:
   GET /posts to fetch all posts.
   POST /posts to create a new post (requires authentication).
   PUT /posts/:id to update an existing post (authorization required).
   DELETE /posts/:id to delete a post (authorization required).
4. Frontend Integration
   Ensured that all API responses returned clean, structured, and appropriate JSON data for the frontend to consume:
   json
   Copy code
   {
   "id": 1,
   "title": "My First Post",
   "body": "This is an example post body.",
   "image": "https://example.com/image.png",
   "user": {
   "id": 1,
   "name": "John Doe",
   "email": "john@example.com"
   }
   }
   Handled edge cases such as invalid data submissions, unauthorized access, and resource not found with descriptive error messages.
5. Testing
   Wrote comprehensive RSpec tests for all models and controllers:
   Validated relationships between users and posts.
   Tested user authentication flow, ensuring secure login and session handling.
   Verified all API responses for accuracy and integrity.
   Database Schema
   Users Table
   Column Type Details
   id integer Primary Key
   name string Name of the user
   email string Email (unique)
   password_digest string Securely hashed password
   created_at datetime Timestamp
   updated_at datetime Timestamp
   Posts Table
   Column Type Details
   id integer Primary Key
   user_id integer Foreign Key (to users)
   title string Title of the post
   body text Content of the post
   image string URL of the post image
   created_at datetime Timestamp
   updated_at datetime Timestamp
   Skills Demonstrated
   Relational Databases:

Designed a clean schema with appropriate relationships and data integrity constraints.
Wrote migrations to manage database structure effectively.
Authentication:

Secured user data with hashed passwords.
Implemented middleware to guard routes from unauthorized access.
Backend API Development:

Developed RESTful endpoints and ensured consistent JSON responses.
Focused on robust error handling and edge case management.
Testing and Debugging:

Used RSpec for unit and integration tests.
Debugged issues with ActiveRecord and API responses to ensure correctness.
Frontend Collaboration:

Communicated effectively with frontend developers by providing well-structured and predictable API responses.
# demo-mini-capstone-api
# demo-mini-capstone-api

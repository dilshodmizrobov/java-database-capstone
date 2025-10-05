# Schema Design - Java Database Capstone Project

## Database Overview

This database schema is designed for a **Task Management System** where users can create, update, delete, and view tasks. The schema contains tables to store information about users, tasks, and their respective statuses.

---

## 1. Users Table

### Table Name: `users`

| Column Name    | Data Type     | Description                                    |
|----------------|---------------|------------------------------------------------|
| `user_id`      | INT (Primary Key, Auto Increment) | Unique identifier for each user. |
| `first_name`   | VARCHAR(100)   | User's first name.                             |
| `last_name`    | VARCHAR(100)   | User's last name.                              |
| `email`        | VARCHAR(255)   | User's email address (unique).                 |
| `password`     | VARCHAR(255)   | Encrypted user password for authentication.    |
| `role`         | ENUM('admin', 'user') | Role of the user, either 'admin' or 'user'. |
| `created_at`   | TIMESTAMP      | Timestamp of when the user was created.        |
| `updated_at`   | TIMESTAMP      | Timestamp of when the user was last updated.   |

---

## 2. Tasks Table

### Table Name: `tasks`

| Column Name    | Data Type     | Description                                    |
|----------------|---------------|------------------------------------------------|
| `task_id`      | INT (Primary Key, Auto Increment) | Unique identifier for each task. |
| `user_id`      | INT (Foreign Key) | References the `user_id` from the `users` table. |
| `title`        | VARCHAR(255)   | Title of the task.                             |
| `description`  | TEXT           | Detailed description of the task.              |
| `due_date`     | DATE           | Due date of the task.                          |
| `status`       | ENUM('pending', 'in-progress', 'completed') | Status of the task. |
| `priority`     | ENUM('low', 'medium', 'high') | Priority of the task. |
| `created_at`   | TIMESTAMP      | Timestamp when the task was created.           |
| `updated_at`   | TIMESTAMP      | Timestamp when the task was last updated.      |

---

## 3. Task Comments Table

### Table Name: `task_comments`

| Column Name    | Data Type     | Description                                    |
|----------------|---------------|------------------------------------------------|
| `comment_id`   | INT (Primary Key, Auto Increment) | Unique identifier for each comment. |
| `task_id`      | INT (Foreign Key) | References the `task_id` from the `tasks` table. |
| `user_id`      | INT (Foreign Key) | References the `user_id` from the `users` table. |
| `comment`      | TEXT           | Content of the comment.                        |
| `created_at`   | TIMESTAMP      | Timestamp of when the comment was made.        |

---

## 4. Task Attachments Table

### Table Name: `task_attachments`

| Column Name    | Data Type     | Description                                    |
|----------------|---------------|------------------------------------------------|
| `attachment_id`| INT (Primary Key, Auto Increment) | Unique identifier for each attachment. |
| `task_id`      | INT (Foreign Key) | References the `task_id` from the `tasks` table. |
| `file_name`    | VARCHAR(255)   | Name of the file attached to the task.         |
| `file_path`    | VARCHAR(255)   | Path where the file is stored.                 |
| `created_at`   | TIMESTAMP      | Timestamp of when the attachment was added.    |

---

## 5. Task Categories Table (Optional)

### Table Name: `task_categories`

| Column Name    | Data Type     | Description                                    |
|----------------|---------------|------------------------------------------------|
| `category_id`  | INT (Primary Key, Auto Increment) | Unique identifier for each category. |
| `category_name`| VARCHAR(255)   | Name of the category (e.g., "Work", "Personal"). |
| `description`  | TEXT           | A description of the category.                 |

---

## Relationships Between Tables

1. **Users ↔ Tasks**
   - A user can have multiple tasks.
   - The `user_id` in the `tasks` table is a foreign key referencing the `users` table.

2. **Tasks ↔ Task Comments**
   - A task can have multiple comments.
   - The `task_id` in the `task_comments` table is a foreign key referencing the `tasks` table.
   - Each comment also references a `user_id` to track which user posted the comment.

3. **Tasks ↔ Task Attachments**
   - A task can have multiple attachments.
   - The `task_id` in the `task_attachments` table is a foreign key referencing the `tasks` table.

4. **Tasks ↔ Task Categories (Optional)**
   - A task can belong to a category (like "Work", "Personal", etc.).
   - The `category_id` in the `tasks` table is a foreign key referencing the `task_categories` table (if you choose to implement this).

---

## Example SQL Queries

1. **Create a new task**:

```sql
INSERT INTO tasks (user_id, title, description, due_date, status, priority, created_at)
VALUES (1, 'Finish Project', 'Complete the final project for the capstone course.', '2025-10-10', 'pending', 'high', NOW());


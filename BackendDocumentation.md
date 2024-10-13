# BackendDocumentation

- Backend API Endpoint for the Social Media App
- Auth with Supabase in Frontend and a Backend API Endpoint for the User Credentials, Email is directly handled by the Backend

# Objectives

- User (Object)
  - Username (String)
  - role (String) (User, Moderator, Admin)
  - Karma (int) 
  - created_at (timestamp)
  - updated_at (timestamp)
  - optional Picture
  - Badges (Badges that the user has earned)
  - Tasks (Tasks that the user has posted)
  - Comments (Comments that the user has made)
  - optional: Bio

- tasks (Object)
    - `id` (String)
    - `title` (String)
    - `description` (String)
    - `braincells` (int)
    - `category` (String) (optional)
    - `picture` (String) (optional)
    - `tags` (Array) (optional)
    - `comments` (Array) (Comments that the task has)
    - `upvotes` (int)
    - `downvotes` (int)
    - `created_at` (timestamp)
    - `updated_at` (timestamp)


## Endpoints

- `/api/v1/auth/signup` - POST
  - Request Body: 
    - `email` (String)
    - `password` (String)
  - Response: 
    - `token` (String)
    - `user` (Object)
      - `id` (String)
      - `email` (String)
      - `created_at` (String)
      - `updated_at` (String)

- `/api/v1/auth/login` - POST
  - Request Body: 
    - `email` (String)
    - `password` (String)
    - Response:
    - `token` (String)
    - `user` (Object)
      - `id` (String)
      - `email` (String)
      - `created_at` (String)
      - `updated_at` (String)
      
- `/api/v1/auth/logout` - POST
  - Request Body: 
    - `token
    - Response:
    - `message` (String)

- `/api/v1/users/:id` - GET
  - Request Body: 
    - `userID` or `username`
    - Response:
      - user (Object)
        - `id` (String)
        - `email` (String)
        - `role` (String) (User, Moderator, Admin)
        - `created_at` (timestamp)
        - `updated_at` (timestamp)
        - `karma` (int) 
        - `picture` (String) (optional)
        - `bio` (String) (optional)
        - `badges` (Array) (Badges that the user has earned)
        - `tasks` (Array) (Tasks that the user has posted)
        - `comments` (Array) (Comments that the user has made)
      
- `/api/v1/users/:id/tasks` - GET
    - Request Body: 
      - `userID` or `username`
    - Response:
      - tasks (Array)
        - `id` (String)
        - `title` (String)
        - `description` (String)
        - `braincells` (int)
        - `category` (String) (optional)
        - `picture` (String) (optional)
        - `tags` (Array) (optional)
        - `comments` (Array) (Comments that the task has)
        - `upvotes` (int)
        - `downvotes` (int)
        - `created_at` (timestamp)
        - `updated_at` (timestamp)

- `/api/v1/tasks/filter - GET
    - Request Body: 
      - `title` (String)
      - `tags` (String)
      - `braincells` (int)
      - `userID` or `username`
      - `upvotes` (int)
      - `downvotes` (int)
      - `comments` (int)
      - `picture` (Boolean)
      - `category` (String)
    - Response:
      - tasks (Array)
        - `id` (String)
        - `title` (String)
        - `description` (String)
        - `braincells` (int)
        - `category` (String) (optional)
        - `picture` (String) (optional)
        - `tags` (Array) (optional)
        - `comments` (Array) (Comments that the task has)
        - `upvotes` (int)
        - `downvotes` (int)
        - `created_at` (timestamp)
        - `updated_at` (timestamp)

- `/api/v1/tasks/all` - GET
    - Request Body: 
    - Response:
      - tasks (Array) (100 at a time)
        - `id` (String)
        - `title` (String)
        - `description` (String)
        - `braincells` (int)
        - `category` (String) (optional)
        - `picture` (String) (optional)
        - `tags` (Array) (optional)
        - `comments` (Array) (Comments that the task has)
        - `upvotes` (int)
        - `downvotes` (int)
        - `created_at` (timestamp)
        - `updated_at` (timestamp)

- `/api/v1/tasks/create` - POST
    - Request Body: 
      - `title` (String)
      - `description` (String)
      - `braincells` (int)
      - `category` (String) (optional)
      - `picture` (String) (optional)
      - `tags` (Array) (optional)
    - Response:
      - `message` (String) (Response Message)

- `/api/v1/tasks/:id` - GET
    - Request Body: 
      - `taskID`
    - Response:
      - task (Object)
        - `id` (String)
        - `title` (String)
        - `description` (String)
        - `braincells` (int)
        - `category` (String) (optional)
        - `picture` (String) (optional)
        - `tags` (Array) (optional)
        - `comments` (Array) (Comments that the task has)
        - `upvotes` (int)
        - `downvotes` (int)
        - `created_at` (timestamp)
        - `updated_at` (timestamp)

- `/api/v1/tasks/:id/upvote` - POST
    - Request Body: 
      - `taskID`
    - Response:
      - `message` (String) (Response Message)

- `/api/v1/tasks/:id/downvote` - POST
    - Request Body: 
      - `taskID`
    - Response:
      - `message` (String) (Response Message)

- `/api/v1/tasks/:id/comment` - POST
    - Request Body: 
        - `token` 
        - `taskID`
        - `comment` (String)
    - Response:
      - `message` (String) (Response Message)

- `/api/v1/tasks/:id/report` - POST
  - Request Body: 
      - `token` 
      - `taskID`
  - Response:
    - `message` (String) (Response Message)

- `/api/v1/tasks/:id/delete` - POST
  - Request Body: 
      - `token` 
      - `taskID`
  - Response:
    - `message` (String) (Response Message)

- `/api/v1/tasks/:id/comment/delete` - POST
    - Request Body: 
        - `token` 
        - `taskID`
        - `commentID`
    - Response:
        - `message` (String) (Response Message)

- `/api/v1/taskss/:id/comments/` - POST
  - Request Body: 
      - `taskID`
  - Response:
    - comments (Array)
      - `id` (String)
      - `comment` (String)
      - `created_at` (timestamp)
      - `updated_at` (timestamp)

- `/api/v1/moderator/reported/all` - GET
  - Request Body: 
    - `token`
  - Response:
    - tasks (Array)
      - `id` (String)
      - `title` (String)
      - `description` (String)
      - `braincells` (int)
      - `category` (String) (optional)
      - `picture` (String) (optional)
      - `tags` (Array) (optional)
      - `comments` (Array) (Comments that the task has)
      - `upvotes` (int)
      - `downvotes` (int)
      - `created_at` (timestamp)
      - `updated_at` (timestamp)

- `/api/v1/moderator/users/:id/ban` - POST
  - Request Body: 
    - `token`
    - `userID`
  - Response:
    - `message` (String) (Response Message)

- `/api/v1/moderator/users/:id/unban` - POST
  - Request Body: 
      - `token`
      - `userID`
  - Response:
    - `message` (String) (Response Message)
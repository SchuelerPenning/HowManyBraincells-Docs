# HowManyBraincells

Social Media Platform: 
- Domain: Braincells.net
- Description: A social media platform that allows users to post tasks and how many braincells it takes to complete the task. You can comment, upvote or downvote a post.

## Features
- Login with Oauth with Google, Discord, Twitter, Facebook, Email
  - Auth with Supabase in Frontend and a Backend API Endpoint for the User Credentials, Email is directly handled by the Backend
- optional: Picture Upload
- Post a Task
  - Title
  - Description
  - Braincells
  - optional: Category
  - optional: Picture Upload
  - optional: Tags
- Comment on a Task
- Upvote or Downvote a Task
- Report a Task
- Search for a Task
  - by Title (String)
  - by Tags (String)
  - by Braincells (int)
  - by User (userID, Username)
  - by Upvotes (int)
  - by Downvotes (int)
  - by Comments (int)
  - by Picture (Boolean)
  - by Category (String)
- Badges
  - User has posted a Task (1, 10, 100, 1000, 10000)
  - User has commented on a Task (1, 10, 100, 1000, 10000)
  - User has upvoted a Task (1, 10, 100, 1000, 10000)
  - User has downvoted a Task (1, 10, 100, 1000, 10000)
- Karma
  - User has posted a Task (+1)
  - User has commented on a Task (+1)
  - User's task was commented on (+1)
  - User's task was upvoted (+1)
  - User's task was downvoted (-1)
  - User's task was deleted by Moderator (-100)
  - User's comment was deleted by Moderator (-50)
- User Profile
  - Username (String)
  - Karma (int)
  - optional Picture
  - Badges
  - Tasks
  - Comments
  - optional: Bio

- Moderator
  - Delete Task
  - Delete Comment
  - Ban User
  - Unban User

- Moderator Dashboard
    - List of all Tasks
    - List of all Comments
    - List of all Users
    - List of all Banned Users
    - List of all Reported Tasks
    - List of all Reported Comments
    - List of the accounts age
    - List of the accounts Karma

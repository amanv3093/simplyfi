# Article Management

## Overview

This project is a backend system built with Node.js and MongoDB. It features:

- Article management with tracking of views and likes.
- User management with notifications.
- Caching for popular articles using Redis.

## Features

- Articles Table: Stores article details including id, title, author, body, number of likes, and number of views.
- Users Table: Stores user details including id and name.
- Tracking Tables: Tracks which articles are liked and viewed by users.
- Caching: Uses Redis to cache views and likes for popular articles.
- Notification System: Sends notifications to users when their articles are liked.

# API Endpoints

## Users
 ```Users 
 https://simplyfi-d1va.onrender.com/users
   ```
- GET /users: Retrieve all users.
- POST /users: Create a new user.
- GET /users/
  : Retrieve a specific user by ID.

## Articles

 ```Articles 
 https://simplyfi-d1va.onrender.com/articles
   ```
- GET /articles: Retrieve all articles.
- POST /articles: Create a new article.
- GET /articles/
  : Retrieve a specific article by ID.
- PUT /articles/
  : Update a specific article by ID.
- DELETE /articles/
  : Delete a specific article by ID.



## Article Likes and Views
 ```Article Likes and Views 
 https://simplyfi-d1va.onrender.com/articles/:id/like
   ```
- POST /articles/
  /like: Like an article.
- POST /articles/
  /view: View an article.

## Notifications
  ```Notifications 
  https://simplyfi-d1va.onrender.com/users/:id/notifications
   ```
- GET /notifications: Retrieve all notifications.
- POST /notifications: Create a new notification.

## Caching

The system uses Redis to cache views and likes for popular articles. Configure Redis with the provided REDIS_URL in your .env file.

# Database Schema

## Articles Table

- `id`: Unique identifier (e.g., ObjectId)
- `title`: String
- `author`: String
- `body`: String
- `likes`: Number
- `views`: Number

## Users Table

- `id`: Unique identifier (e.g., ObjectId)
- `name`: String

## Likes Table

- `userId`: Unique identifier of the user
- `articleId`: Unique identifier of the article

## Views Table

- `userId`: Unique identifier of the user
- `articleId`: Unique identifier of the article

## Notifications Table

- `userId`: Unique identifier of the user
- `articleId`: Unique identifier of the article
- `message`: String
- `timestamp`: Date

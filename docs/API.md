# API Documentation

## Authentication Routes

### `POST /auth/register`
- **Request Body:**
  - `username`: string
  - `password`: string

- **Response:**
  - `201 Created` on successful registration.
  - Example:
    ```json
    {
      "message": "User registered successfully."
    }
    ```

### `POST /auth/login`
- **Request Body:**
  - `username`: string
  - `password`: string

- **Response:**
  - `200 OK` on successful login.
  - Example:
    ```json
    {
      "token": "..."
    }
    ```

### `GET /auth/me`
- **Headers:**
  - `Authorization: Bearer {token}`

- **Response:**
  - `200 OK` with user details.
  - Example:
    ```json
    {
      "username": "user",
      "email": "user@example.com"
    }
    ```

## Quiz Routes

### `POST /quiz/generate`
- **Request Body:**
  - `topic`: string

- **Response:**
  - `200 OK` with generated questions.
  - Example:
    ```json
    {
      "questions": [ ... ]
    }
    ```

### `POST /quiz/submit`
- **Request Body:**
  - `answers`: array of objects

- **Response:**
  - `200 OK` with quiz results.
  - Example:
    ```json
    {
      "score": 85,
      "total": 100
    }
    ```

## Gamification Routes

### `GET /gamification/leaderboard`
- **Response:**
  - `200 OK` with leaderboard data.
  - Example:
    ```json
    [{
      "username": "user1",
      "score": 150
    }]
    ```

### `GET /gamification/user/{id}/stats`
- **Response:**
  - `200 OK` with user stats.
  - Example:
    ```json
    {
      "userId": 1,
      "coins": 100
    }
    ```

### `POST /gamification/add-coins`
- **Request Body:**
  - `userId`: integer
  - `amount`: integer

- **Response:**
  - `200 OK` on success.
  - Example:
    ```json
    {
      "message": "Coins added successfully."
    }
    ```

### `GET /gamification/achievements`
- **Response:**
  - `200 OK` with list of achievements.
  - Example:
    ```json
    [{
      "achievement": "First Quiz Completed",
      "date": "2023-01-01"
    }]
    ```

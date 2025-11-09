# Jokes API 😂 

A simple **RESTful API** built with **Node.js** and **Express.js** that allows users to manage a collection of jokes.
You can **create**, **read**, **update**, **delete**, and **filter** jokes by type.  

## Features

* Get a random joke
* Get all jokes or a specific joke by ID
* Add a new joke
* Update or partially update an existing joke
* Delete a single joke or all jokes (with a master key)
* Filter jokes by type (e.g., Science, Puns, Dad Jokes)


## Technologies Used

* [Node.js](https://nodejs.org/)
* [Express.js](https://expressjs.com/)


## Installation & Setup

  ### 1. Clone the repository

```bash
git clone https://github.com/your-username/jokes-api.git
cd jokes-api
```

### 2. Install dependencies

```bash
npm install
```

### 3. Run the server

```bash
node index.js
```

Server will start on:

```
http://localhost:3000
```


## API Endpoints

### Get all jokes

```
GET /jokes
```

### Get a random joke

```
GET /random
```

### Get a specific joke by ID

```
GET /jokes/:id
```

Example:

```
GET /jokes/2
```

### Filter jokes by type

```
GET /filter?type=Science
```

---

### Add a new joke

```
POST /jokes
```

**Body (JSON):**

```json
{
  "type": "Dad",
  "text": "I'm reading a book on anti-gravity. It's impossible to put down."
}
```

---

### Update (replace) a joke

```
PUT /jokes/:id
```

**Body (JSON):**

```json
{
  "type": "Pun",
  "text": "Why did the math book look sad? Because it had too many problems."
}
```

---

### Partially update a joke

```
PATCH /jokes/:id
```

**Body (JSON):**

```json
{
  "text": "New version of the joke text only."
}
```

---

### Delete a joke

```
DELETE /jokes/:id
```

Example:

```
DELETE /jokes/3
```

---

### Delete all jokes (requires a key)

```
DELETE /jokes?key=4VGP2DN-6EWM4SJ-N6FGRHV-Z3PR3TT
```
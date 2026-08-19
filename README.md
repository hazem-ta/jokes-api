# Jokes REST API

A small REST API built with Node.js and Express for managing an in-memory collection of jokes. It demonstrates resource routing, filtering, full and partial updates, and protected destructive operations.

## Features

- Retrieve all jokes, one joke by ID, or a random joke
- Filter jokes by category
- Create, replace, and partially update jokes
- Delete individual jokes
- Protect bulk deletion with a server-side key supplied through a request header

## Run locally

```bash
git clone https://github.com/hazem-ta/jokes-api.git
cd jokes-api
npm install
```

Copy `.env.example` to `.env`, replace the example key, then start the server:

```bash
npm start
```

The API runs at `http://localhost:3000` by default. Data is held in memory and resets when the server restarts.

## Configuration

| Variable | Purpose | Default |
| --- | --- | --- |
| `PORT` | HTTP server port | `3000` |
| `MASTER_KEY` | Authorizes bulk deletion | None |

Never commit `.env`. Generate a long random value for `MASTER_KEY` outside the repository.

## Endpoints

| Method | Endpoint | Description |
| --- | --- | --- |
| `GET` | `/jokes` | Return all jokes |
| `GET` | `/jokes/:id` | Return one joke |
| `GET` | `/random` | Return a random joke |
| `GET` | `/filter?type=Science` | Filter by category |
| `POST` | `/jokes` | Create a joke |
| `PUT` | `/jokes/:id` | Replace a joke |
| `PATCH` | `/jokes/:id` | Update selected fields |
| `DELETE` | `/jokes/:id` | Delete one joke |
| `DELETE` | `/jokes` | Delete all jokes |

Create and update requests accept JSON:

```json
{
  "type": "Dad",
  "text": "I'm reading a book on anti-gravity. It's impossible to put down."
}
```

Bulk deletion requires the configured key in a header:

```bash
curl -X DELETE http://localhost:3000/jokes \
  -H "x-api-key: your-local-master-key"
```

## Notes

This project intentionally uses in-memory data to focus on HTTP and REST behavior. A production version would add persistent storage, schema validation, tests, rate limiting, and centralized error handling.

## Author

[Hazem Ahmed](https://github.com/hazem-ta)

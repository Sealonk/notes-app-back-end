# Notes App Back-End

This is a simple back-end application for managing notes. The server is built using Hapi.js and provides a RESTful API with CRUD operations to create, read, update, and delete notes.

## Features

- **Add Notes**: Create a new note with a title, tags, and body.
- **View All Notes**: Retrieve a list of all notes.
- **View Note by ID**: Retrieve the details of a specific note by its ID.
- **Edit Notes**: Update the details of an existing note.
- **Delete Notes**: Remove a note from the list.

## Technologies Used

- [Hapi.js](https://hapi.dev/): Web framework for building the server.
- [Node.js](https://nodejs.org/): JavaScript runtime used for server-side development.

## Setup

To get started with this project locally, follow these steps:

### 1. Clone the repository

```bash
git clone https://github.com/Sealonk/notes-app-back-end.git
```

### 2. Install dependencies

```bash
cd notes-app-back-end
npm install
```

### 3. Run the appliation

To start the server,run:
```bash
npm run start
```

The server will start running at `http://localhost:5000`.

### 4. Test the API

You can test the API endpoints using tools like [Postman](https://www.postman.com/) or [curl](https://curl.se/).

## API Endpoints

### `POST /notes`

Create a new note.

#### Request:

```json
{
  "title": "My Note",
  "tags": ["personal", "important"],
  "body": "This is the content of the note."
}
```

#### Response:

```json
{
  "status": "success",
  "message": "Catatan berhasil ditambahkan",
  "data": {
    "noteId": "unique-note-id"
  }
}
```

### `GET /notes`

Retrieve all notes.

#### Response:

```json
{
  "status": "success",
  "data": {
    "notes": [
      {
        "id": "unique-note-id",
        "title": "My Note",
        "tags": ["personal", "important"],
        "body": "This is the content of the note.",
        "createdAt": "2024-12-14T12:00:00Z",
        "updatedAt": "2024-12-14T12:00:00Z"
      }
    ]
  }
}
```

### `GET /notes/v`

Retrieve a note by its ID.

#### Response:

```json
{
  "status": "success",
  "data": {
    "note": {
      "id": "unique-note-id",
      "title": "My Note",
      "tags": ["personal", "important"],
      "body": "This is the content of the note.",
      "createdAt": "2024-12-14T12:00:00Z",
      "updatedAt": "2024-12-14T12:00:00Z"
    }
  }
}
```

### `PUT /notes/{id}`

Update an existing note by its ID.

#### Request:

```json
{
  "title": "Updated Note",
  "tags": ["work"],
  "body": "This is the updated content of the note."
}
```

#### Response:

```json
{
  "status": "success",
  "message": "Catatan berhasil diperbarui"
}
```

### `DELETE /notes/{id}`

Delete a note by its ID.

#### Response:

```json
{
  "status": "success",
  "message": "Catatan berhasil dihapus"
}
```

## Folder Structure

```bash
- node_modules/
- src/
  - handler.js      # Contains all handler functions for the API
  - notes.js        # Stores the list of notes
  - routes.js       # Defines API routes and their handlers
  - server.js       # Initializes and starts the Hapi.js server
- .gitignore        # Git ignore file
- eslint.config.mjs # ESLint configuration file
- package.json      # Project metadata and dependencies
- README.md         # Project documentation
```

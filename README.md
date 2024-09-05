# Movie CRUD API

This is a simple RESTful API built with Go (Golang) that manages a collection of movies. It allows you to create, read, update, and delete movie records.
## Features

- **Create**: Add new movies to the collection.
- **Read**: Fetch a list of all movies or get a specific movie by ID.
- **Update**: Modify the details of an existing movie.
- **Delete**: Remove a movie from the collection.

## Endpoints
### 1. Get All Movies

   - **URL**: `/movies`
   - **Method**: `GET`
   - **Description**: Retrieves the list of all movies.
   - **Response**: JSON array of movies.

   Example:
   ```bash
    curl -X GET http://localhost:8000/movies
   ```

### 2. Get Movie by ID

  - **URL**: /movies/{id}
  - **Method**: GET
  - **Description**: Retrieves a movie by its unique ID.
  - **Response**: JSON object of the requested movie.

Example:

```bash

curl -X GET http://localhost:8000/movies/{id}
```

### 3. Create a New Movie

 - **URL**: /movies
 - **Method**: POST
 - **Description**: Adds a new movie to the collection.
 - **Request Body**: JSON object with the movie details.

Example:
```
json

{
  "isbn": "438227",
  "title": "Inception",
  "director": {
    "firstname": "Christopher",
    "lastname": "Nolan"
  }
}
```
Example:

```bash

curl -X POST -H "Content-Type: application/json" -d '{"isbn":"438227","title":"Inception","director":{"firstname":"Christopher","lastname":"Nolan"}}' http://localhost:8000/movies
```
### 4. Update a Movie

  - **URL**: /movies/{id}
  - **Method**: PUT
  - **Description**: Updates an existing movie by its unique ID.
  - **Request Body**: JSON object with updated movie details.

Example:

```bash

curl -X PUT -H "Content-Type: application/json" -d '{"isbn":"438228","title":"Interstellar","director":{"firstname":"Christopher","lastname":"Nolan"}}' http://localhost:8000/movies/{id}
```
### 5. Delete a Movie

  - **URL**: /movies/{id}
  -  **Method**: DELETE
  - **Description**: Removes a movie by its unique ID.

Example:

```bash

curl -X DELETE http://localhost:8000/movies/{id}
```
## Running the Project

  **Clone the repository**:

  ```bash

git clone https://github.com/Abderrahmanehocine/go-movies-crud
cd go-movies-crud
```

**Install dependencies**:

- Make sure you have Gorilla Mux installed. If not, install it:

```bash

go get -u github.com/gorilla/mux
```
**Run the server**:

Start the Go server on port 8000:

```bash

    go run main.go
```
  **Access the API**:

  The server will be available at http://localhost:8000/.

## Project Structure

```bash

.
├── main.go        # The main Go file that contains the API code
└── README.md      # The README file
```
## Tools Used

  - **Gorilla Mux**: HTTP router and URL matcher for building Go web servers.
  - **net/http**: Standard Go package for building web applications.
  - **encoding/json**: Standard Go package for encoding and decoding JSON.

## License

**This project is open-source and available under the MIT License.**

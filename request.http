GET  https://api.themoviedb.org/3/discover/movie

GET http://localhost:1337/api/movies

GET http://localhost:1337/api/movies?populate=*

GET http://localhost:1337/api/movies?populate=actors

GET http://localhost:1337/api/movies?filters[title][$startsWith]=H

GET http://localhost:1337/api/movies/1?populate=actors

POST http://localhost:1337/api/movies
{"data": 
    {"createdAt": "2023-11-08T08:48:30.533Z",
            "updatedAt": "2023-11-08T09:49:26.842Z",
            "publishedAt": "2023-11-08T08:49:54.577Z",
            "title": "API",
            "description": "Super cours d'API youhou",
            "releaseDate": "2023-11-08",
            "director": "BNI"
    }
}

POST http://localhost:1337/api/auth/local
{
    "identifier" : "nicolas.borlet7@gmail.com",
    "password" : "Buran.73600"
}

POST http://localhost:1337/api/auth/local/register
{
    "username": "Kapman",
    "email": "test@test.com",
    "password": "Password.12345"
}

//GraphQL queries and mutations
//GET
query {
  movies {
    data {
      attributes {
        title
        description
        actors {
          data {
            id
            attributes {
              lastName
              firstName
            }
          }
        }
      }
    }
  }
}

//GET ONLY ONE WITH FIRST LETTER IS H
query {
  movies(filters: {
    title: { startsWith: "H" }
  }) {
    data {
      attributes {
        title
        description
        actors {
          data {
            id
            attributes {
              lastName
              firstName
            }
          }
        }
      }
    }
  }
}

//POST
mutation createMovie {
  createMovie(data: {title: "Hello"}) {
    data {
      id
      attributes {
        title
      }
    }
  }
}

//UPDATE
mutation updateMovie {
  updateMovie(id: "1", data: {title: "HellowWold"}) {
    data {
      id
      attributes {
        title
      }
    }
  }
}

//DELETE
mutation deleteMovie {
  deleteMovie(id: 1) {
    data {
      id
      attributes {
        title
      }
    }
  }
}

//CREATION USER
mutation {
  register(
    input: {
      username: "alloyuser1"
      email: "email1@gmail.com"
      password: "password.12345"
    }
  ) {
    jwt
    user {
      username
      email
    }
  }
}

//LOGIN
mutation {
  login(input: { identifier: "email1@gmail.com", password: "password.12345" }) {
    jwt
  }
}

//GET WITH AUTH
//ADD JWT IN HEADER
{"Authorization": "Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MywiaWF0IjoxNjk5NDUzMzg3LCJleHAiOjE3MDIwNDUzODd9.Zwl8dWn3FLJY9EgWOuBb7vM3EzM3JTiuQ-lpSpU659w"}
//GET
query {
  movies {
    data {
      attributes {
        title
        description
        actors {
          data {
            id
            attributes {
              lastName
              firstName
            }
          }
        }
      }
    }
  }
}

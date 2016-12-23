# Users

## Get All Users

```shell
curl -X GET -H "Authorization: Bearer token" -H
"Content-Type: application/vnd.api+json" "http://localhost:3000/users/"
```

> The above command returns JSON structured like this:

```json
[
{
  "data": [
  {
    "id": "1",
      "type": "users",
      "links": {
        "self": "http://localhost:3000/users/1"
      },
      "attributes": {
        "name": "Keegan Aufderhar",
        "email": "americo_goodwin@mcdermottsatterfield.org"
      },
      "relationships": {
        "rounds": {
          "links": {
            "self": "http://localhost:3000/users/1/relationships/rounds",
            "related": "http://localhost:3000/users/1/rounds"
          }
        },
        "scores": {
          "links": {
            "self": "http://localhost:3000/users/1/relationships/scores",
            "related": "http://localhost:3000/users/1/scores"
          }
        }
      }
  },
  {
    "id": "2",
    "type": "users",
    "links": {
      "self": "http://localhost:3000/users/2"
    },
    "attributes": {
      "name": "Matthew McQuinn",
      "email": "mmcquinn77@gmail.com"
    },
    "relationships": {
      "rounds": {
        "links": {
          "self": "http://localhost:3000/users/2/relationships/rounds",
          "related": "http://localhost:3000/users/2/rounds"
        }
      },
      "scores": {
        "links": {
          "self": "http://localhost:3000/users/2/relationships/scores",
          "related": "http://localhost:3000/users/2/scores"
        }
      }
    }
  }
  ]
}
]
```

This endpoint retrieves all users.

### HTTP Request

`GET http://localhost:3000/users`

### Query Parameters

## Get a Specific User

```shell
curl -X GET -H "Authorization: Bearer token"
-H "Content-Type: application/vnd.api+json" "http://localhost:3000/users/1"
```

> The above command returns JSON structured like this:

```json
{
  "data": {
    "id": "1",
      "type": "users",
      "links": {
        "self": "http://localhost:3000/users/1"
      },
      "attributes": {
        "name": "Keegan Aufderhar",
        "email": "americo_goodwin@mcdermottsatterfield.org"
      },
      "relationships": {
        "rounds": {
          "links": {
            "self": "http://localhost:3000/users/1/relationships/rounds",
            "related": "http://localhost:3000/users/1/rounds"
          }
        },
        "scores": {
          "links": {
            "self": "http://localhost:3000/users/1/relationships/scores",
            "related": "http://localhost:3000/users/1/scores"
          }
        }
      }
  }
}
```

This endpoint retrieves a specific user.


### HTTP Request

`GET http://example.com/users/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the user to retrieve

## Create a user

```shell
curl -X POST -H "Content-Type: application/vnd.api+json"
-d '{
  data": {
    "type": "users",
    "attributes": {
      "name": "Philo Brathwaite",
      "email": "mralbatross@gmail.com",
      "password": "dg4life"
    }
  }
}
' "http://localhost:3000/users"
```

> The above command returns JSON structured like this:

```json
{
  "data": {
    "id": "1",
    "type": "users",
    "links": {
      "self": "http://localhost:3000/users/1"
    },
    "attributes": {
      "name": "Philo Brathwaite",
      "email": "mralbatross@gmail.com"
    },
    "relationships": {
      "rounds": {
        "links": {
          "self": "http://localhost:3000/users/1/relationships/rounds",
          "related": "http://localhost:3000/users/1/rounds"
        }
      },
      "scores": {
        "links": {
          "self": "http://localhost:3000/users/1/relationships/scores",
          "related": "http://localhost:3000/users/1/scores"
        }
      }
    }
  }
}
```

This endpoint creates a user.

### HTTP Request

`POST http://localhost:3000/users`

## Update a user

```shell
curl -X PUT -H "Authorization: Bearer token" -H "Content-Type: application/vnd.api+json" -d '{
  "data": {
    "type": "users",
      "id": 1,
      "attributes": {
        "email": "philo@gmail.com"
      }
  }
}' "http://localhost:3000/users/1"
```

> The above command returns JSON structured like this:

```json
{
  "data": {
    "id": "1",
    "type": "users",
    "links": {
      "self": "http://localhost:3000/users/1"
    },
    "attributes": {
      "name": "Philo Brathwaite",
      "email": "philo@gmail.com"
    },
    "relationships": {
      "rounds": {
        "links": {
          "self": "http://localhost:3000/users/1/relationships/rounds",
          "related": "http://localhost:3000/users/1/rounds"
        }
      },
      "scores": {
        "links": {
          "self": "http://localhost:3000/users/1/relationships/scores",
          "related": "http://localhost:3000/users/1/scores"
        }
      }
    }
  }
}
```

This endpoint updates a user

### HTTP Request

`PUT http://localhost:3000/users/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the user to update

## Delete a user

> Users can only delete themselves

```shell
curl -X DELETE -H "Authorization: Bearer token"
-H "Content-Type: application/vnd.api+json" "http://localhost:3000/users/1"
```

> The above command returns 204 No Content

This endpoint deletes a user

### HTTP Request

`DELETE http://localhost:3000/users/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the user to delete

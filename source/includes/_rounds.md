# Rounds

## Get all rounds

```shell
curl -X GET -H "Authorization: Bearer token" -H "Content-Type: application/vnd.api+json" "http://localhost:3000/rounds"
```

> The above command returns JSON structured like this:

```json
{
"data": [
  {
    "id": "1",
    "type": "rounds",
    "links": {
      "self": "http://localhost:3000/rounds/1"
    },
    "attributes": {
      "weather": "Sunny",
      "score": -5
    },
    "relationships": {
      "scores": {
        "links": {
          "self": "http://localhost:3000/rounds/1/relationships/scores",
          "related": "http://localhost:3000/rounds/1/scores"
        }
      },
      "user": {
        "links": {
          "self": "http://localhost:3000/rounds/1/relationships/user",
          "related": "http://localhost:3000/rounds/1/user"
        }
      },
      "course": {
        "links": {
          "self": "http://localhost:3000/rounds/1/relationships/course",
          "related": "http://localhost:3000/rounds/1/course"
        }
      }
    }
  },
  {
    "id": "2",
    "type": "rounds",
    "links": {
      "self": "http://localhost:3000/rounds/2"
    },
    "attributes": {
      "weather": "Rainy",
      "score": 0
    },
    "relationships": {
      "scores": {
        "links": {
          "self": "http://localhost:3000/rounds/2/relationships/scores",
          "related": "http://localhost:3000/rounds/2/scores"
        }
      },
      "user": {
        "links": {
          "self": "http://localhost:3000/rounds/2/relationships/user",
          "related": "http://localhost:3000/rounds/2/user"
        }
      },
      "course": {
        "links": {
          "self": "http://localhost:3000/rounds/2/relationships/course",
          "related": "http://localhost:3000/rounds/2/course"
        }
      }
    }
  }
]
}
```

This endpoint retrieves all rounds for all users.

### HTTP Request

`GET http://localhost:3000/rounds`

## Get a round

```shell
curl -X GET -H "Authorization: Bearer token" -H "Content-Type: application/vnd.api+json" "http://localhost:3000/rounds/2"
```

> The above command returns JSON structured like this:

```json
{
  "data": {
    "id": "2",
    "type": "rounds",
    "links": {
      "self": "http://localhost:3000/rounds/2"
    },
    "attributes": {
      "weather": "Rainy",
      "score": 0
    },
    "relationships": {
      "scores": {
        "links": {
          "self": "http://localhost:3000/rounds/2/relationships/scores",
          "related": "http://localhost:3000/rounds/2/scores"
        }
      },
      "user": {
        "links": {
          "self": "http://localhost:3000/rounds/2/relationships/user",
          "related": "http://localhost:3000/rounds/2/user"
        }
      },
      "course": {
        "links": {
          "self": "http://localhost:3000/rounds/2/relationships/course",
          "related": "http://localhost:3000/rounds/2/course"
        }
      }
    }
  }
}
```

This endpoint retrieves a single round.

### HTTP Request

`GET http://localhost:3000/rounds/<ID>`

### URL Parameters
Parameter | Description
--------- | -----------
ID | The ID of the round to retrieve

## Create a round

```shell
curl -X POST -H "Authorization: Bearer token" -H "Content-Type: application/vnd.api+json" -d '{
   "data":{
      "type":"rounds",
      "attributes":{
         "weather":"Very Windy"
      },
      "relationships":{
         "user":{
            "data":{
               "type":"users",
               "id":2
            }
         },
         "course":{
            "data":{
               "type":"courses",
               "id":1
            }
         }
      }
   }
}' "http://localhost:3000/rounds"
```

> The above command returns JSON structured like this:

```json
{
  "data": {
    "id": "3",
    "type": "rounds",
    "links": {
      "self": "http://localhost:3000/rounds/3"
    },
    "attributes": {
      "weather": "Very Windy",
      "score": 0
    },
    "relationships": {
      "scores": {
        "links": {
          "self": "http://localhost:3000/rounds/3/relationships/scores",
          "related": "http://localhost:3000/rounds/3/scores"
        }
      },
      "user": {
        "links": {
          "self": "http://localhost:3000/rounds/3/relationships/user",
          "related": "http://localhost:3000/rounds/3/user"
        }
      },
      "course": {
        "links": {
          "self": "http://localhost:3000/rounds/3/relationships/course",
          "related": "http://localhost:3000/rounds/3/course"
        }
      }
    }
  }
}
```

This endpoint creates a round for a user.

### HTTP Request

`POST http://localhost:3000/rounds`

## Update a round

> Users can only update their own rounds

```shell
curl -X PUT -H "Authorization: Bearer token" -H "Content-Type: application/vnd.api+json" -d '{
  "data": {
    "type": "rounds",
    "id": 3,
    "attributes": {
      "weather": "Sunny"
    }
  }
}' "http://localhost:3000/rounds/3"
```

> The above command returns JSON structured like this:

```json
{
  "data": {
    "id": "3",
    "type": "rounds",
    "links": {
      "self": "http://localhost:3000/rounds/3"
    },
    "attributes": {
      "weather": "Sunny",
      "score": 0
    },
    "relationships": {
      "scores": {
        "links": {
          "self": "http://localhost:3000/rounds/3/relationships/scores",
          "related": "http://localhost:3000/rounds/3/scores"
        }
      },
      "user": {
        "links": {
          "self": "http://localhost:3000/rounds/3/relationships/user",
          "related": "http://localhost:3000/rounds/3/user"
        }
      },
      "course": {
        "links": {
          "self": "http://localhost:3000/rounds/3/relationships/course",
          "related": "http://localhost:3000/rounds/3/course"
        }
      }
    }
  }
}
```

This endpoint updates a round

### HTTP Request

`PUT http://localhost:3000/rounds/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the round to update

## Delete a round

> Users can only delete their own rounds

```shell
curl -X DELETE -H "Authorization: Bearer token" -H "Content-Type: application/vnd.api+json" "http://localhost:3000/rounds/3"
```

> The above command returns 204 No Content

This endpoint deletes a user

### HTTP Request

`DELETE http://localhost:3000/rounds/<ID>`

### URL Parameters
Parameter | Description
--------- | -----------
ID | The ID of the round to delete

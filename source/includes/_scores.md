# Scores

## Get all scores

```shell
curl -X GET -H "Authorization: Bearer token" -H "Content-Type: application/vnd.api+json" "http://localhost:3000/scores"
```

> The above command returns JSON structured like this:

```json
{
  "data": [
  {
    "id": "1",
      "type": "scores",
      "links": {
        "self": "http://localhost:3000/scores/1"
      },
      "attributes": {
        "strokes": 1
      },
      "relationships": {
        "hole": {
          "links": {
            "self": "http://localhost:3000/scores/1/relationships/hole",
            "related": "http://localhost:3000/scores/1/hole"
          }
        },
        "user": {
          "links": {
            "self": "http://localhost:3000/scores/1/relationships/user",
            "related": "http://localhost:3000/scores/1/user"
          }
        },
        "round": {
          "links": {
            "self": "http://localhost:3000/scores/1/relationships/round",
            "related": "http://localhost:3000/scores/1/round"
          }
        }
      }
  },
  {
    "id": "2",
    "type": "scores",
    "links": {
      "self": "http://localhost:3000/scores/2"
    },
    "attributes": {
      "strokes": 6
    },
    "relationships": {
      "hole": {
        "links": {
          "self": "http://localhost:3000/scores/2/relationships/hole",
          "related": "http://localhost:3000/scores/2/hole"
        }
      },
      "user": {
        "links": {
          "self": "http://localhost:3000/scores/2/relationships/user",
          "related": "http://localhost:3000/scores/2/user"
        }
      },
      "round": {
        "links": {
          "self": "http://localhost:3000/scores/2/relationships/round",
          "related": "http://localhost:3000/scores/2/round"
        }
      }
    }
  }
  ... and so on...
    ]
}
```

This endpoint retrieves all scores for all users.
This probably isn't very useful.
It is better to get the scores for a user through the users endpoint

### HTTP Request

`GET http://localhost:3000/scores`

## Get a score

```shell
curl -X GET -H "Authorization: Bearer token"
-H "Content-Type: application/vnd.api+json" "http://localhost:3000/scores/1"
```

> The above command returns JSON structured like this:

```json
{
  "data": {
    "id": "1",
      "type": "scores",
      "links": {
        "self": "http://localhost:3000/scores/1"
      },
      "attributes": {
        "strokes": 1
      },
      "relationships": {
        "hole": {
          "links": {
            "self": "http://localhost:3000/scores/1/relationships/hole",
            "related": "http://localhost:3000/scores/1/hole"
          }
        },
        "user": {
          "links": {
            "self": "http://localhost:3000/scores/1/relationships/user",
            "related": "http://localhost:3000/scores/1/user"
          }
        },
        "round": {
          "links": {
            "self": "http://localhost:3000/scores/1/relationships/round",
            "related": "http://localhost:3000/scores/1/round"
          }
        }
      }
  }
}
```

This endpoint retrieves a single score

### HTTP Request

`GET http://localhost:3000/scores/<ID>`

### URL Parameters
Parameter | Description
--------- | -----------
ID | The ID of the score to retrieve

## Create a score

```shell
curl -X POST -H "Authorization: Bearer token"
-H "Content-Type: application/vnd.api+json" -d '{
  "data": {
    "type": "scores",
      "attributes": {
        "strokes": 3
      },
      "relationships": {
        "hole": { "data": { "type": "holes", "id": 1 } },
        "round": { "data": { "type": "rounds", "id": 3 } }
      }
  }
}
' "http://localhost:3000/scores"
```

> The above command returns JSON structured like this:

```json
{
  "data": {
    "id": "19",
      "type": "scores",
      "links": {
        "self": "http://localhost:3000/scores/19"
      },
      "attributes": {
        "strokes": 3
      },
      "relationships": {
        "hole": {
          "links": {
            "self": "http://localhost:3000/scores/19/relationships/hole",
            "related": "http://localhost:3000/scores/19/hole"
          }
        },
        "user": {
          "links": {
            "self": "http://localhost:3000/scores/19/relationships/user",
            "related": "http://localhost:3000/scores/19/user"
          }
        },
        "round": {
          "links": {
            "self": "http://localhost:3000/scores/19/relationships/round",
            "related": "http://localhost:3000/scores/19/round"
          }
        }
      }
  }
}
```

This endpoint creates a score for a round

### HTTP Request

`POST http://localhost:3000/scores`

## Update a score

> Users can only update their own scores

```shell
curl -X PUT -H "Authorization: Bearer token" -H "Content-Type: application/vnd.api+json" -d '{
	"data": {
	    "type": "scores",
	    "id": 37,
	    "attributes": {
	      "strokes": 3
	    }
    }
}
' "http://localhost:3000/scores/37"
```

> The above command returns JSON structured like this:

```json
{
  "data": {
    "id": "37",
    "type": "scores",
    "links": {
      "self": "http://localhost:3000/scores/37"
    },
    "attributes": {
      "strokes": 3
    },
    "relationships": {
      "hole": {
        "links": {
          "self": "http://localhost:3000/scores/37/relationships/hole",
          "related": "http://localhost:3000/scores/37/hole"
        }
      },
      "user": {
        "links": {
          "self": "http://localhost:3000/scores/37/relationships/user",
          "related": "http://localhost:3000/scores/37/user"
        }
      },
      "round": {
        "links": {
          "self": "http://localhost:3000/scores/37/relationships/round",
          "related": "http://localhost:3000/scores/37/round"
        }
      }
    }
  }
}
```

This endpoint updates a score for a user.

### HTTP Request

`PUT http://localhost:3000/scores/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the score to update

## Delete a score

> Users can only delete their own scores

```shell
curl -X DELETE -H "Authorization: Bearer token" -H "Content-Type: application/vnd.api+json" "http://localhost:3000/scores/37"
```

> The above command returns 204 No Content

This endpoint deletes a user's score

### HTTP Request

`DELETE http://localhost:3000/score/<ID>`

### URL Parameters
Parameter | Description
--------- | -----------
ID | The ID of the score to delete

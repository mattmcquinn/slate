# Holes

## Get all holes

> Note: No authentication is required

```shell
curl -X GET -H "Content-Type: application/vnd.api+json" "http://localhost:3000/holes"
```

> The above command returns JSON structured like this:

```json
{
  "data": [
    {
      "id": "1",
      "type": "holes",
      "links": {
        "self": "http://localhost:3000/holes/1"
      },
      "attributes": {
        "number": 1,
        "par": 4
      },
      "relationships": {
        "course": {
          "links": {
            "self": "http://localhost:3000/holes/1/relationships/course",
            "related": "http://localhost:3000/holes/1/course"
          }
        }
      }
    },
    {
      "id": "2",
      "type": "holes",
      "links": {
        "self": "http://localhost:3000/holes/2"
      },
      "attributes": {
        "number": 2,
        "par": 5
      },
      "relationships": {
        "course": {
          "links": {
            "self": "http://localhost:3000/holes/2/relationships/course",
            "related": "http://localhost:3000/holes/2/course"
          }
        }
      }
    },
    {
      "id": "3",
      "type": "holes",
      "links": {
        "self": "http://localhost:3000/holes/3"
      },
      "attributes": {
        "number": 3,
        "par": 3
      },
      "relationships": {
        "course": {
          "links": {
            "self": "http://localhost:3000/holes/3/relationships/course",
            "related": "http://localhost:3000/holes/3/course"
          }
        }
      }
    }
            ... and so on ...
  ]
}
```

This endpoint retrieves all holes for all courses.
This probably isn't very useful.
It is better to get the holes for a course through the courses endpoints

### HTTP Request

`GET http://localhost:3000/holes`

## Get a hole

> Note: No authentication is required

```shell
curl -X GET -H "Content-Type: application/vnd.api+json" "http://localhost:3000/holes/1"
```

> The above command returns JSON structured like this:

```json
{
  "data": {
    "id": "1",
    "type": "holes",
    "links": {
      "self": "http://localhost:3000/holes/1"
    },
    "attributes": {
      "number": 1,
      "par": 4
    },
    "relationships": {
      "course": {
        "links": {
          "self": "http://localhost:3000/holes/1/relationships/course",
          "related": "http://localhost:3000/holes/1/course"
        }
      }
    }
  }
}
```

This endpoint retrieves a hole

### HTTP Request

`GET http://localhost:3000/holes/<ID>`

### URL Parameters
Parameter | Description
--------- | -----------
ID | The ID of the hole to retrieve

## Create a hole

```shell
curl -X POST -H "Authorization: Bearer token" -H "Content-Type: application/vnd.api+json" -d '{
  "data": {
    "type": "holes",
      "attributes": {
        "number": 1,
        "par": 4
      },
      "relationships": {
        "course": { "data": { "type": "courses", "id": 2 } }
      }
  }
}
' "http://localhost:3000/holes"
```

> The above command returns JSON structured like this:

```json
{
  "data": {
    "id": "19",
      "type": "holes",
      "links": {
        "self": "http://localhost:3000/holes/19"
      },
      "attributes": {
        "number": 1,
        "par": 4
      },
      "relationships": {
        "course": {
          "links": {
            "self": "http://localhost:3000/holes/19/relationships/course",
            "related": "http://localhost:3000/holes/19/course"
          }
        }
      }
  }
}
```

This endpoint creates a hole for a course

### HTTP Request

`POST http://localhost:3000/holes`

## Update a hole

```shell
curl -X PUT -H "Authorization: Bearer token" -H "Content-Type: application/vnd.api+json" -d '{
  "data": {
    "type": "holes",
      "id": 17,
      "attributes": {
        "par": 5
      }
  }
}' "http://localhost:3000/holes/17"
```

> The above command returns JSON structured like this:

```json
{
  "data": {
    "id": "17",
      "type": "holes",
      "links": {
        "self": "http://localhost:3000/holes/17"
      },
      "attributes": {
        "number": 17,
        "par": 5
      },
      "relationships": {
        "course": {
          "links": {
            "self": "http://localhost:3000/holes/17/relationships/course",
            "related": "http://localhost:3000/holes/17/course"
          }
        }
      }
  }
}
```

This endpoint updates a hole

### HTTP Request

`PUT http://localhost:3000/holes/<ID>`

### URL Parameters
Parameter | Description
--------- | -----------
ID | The ID of the hole to update

## Delete a hole

```shell
curl -X DELETE -H "Authorization: Bearer token"
-H "Content-Type: application/vnd.api+json" "http://localhost:3000/holes/19"
```

> The above command returns 204 No Content

This endpoint deletes a hole

### HTTP Request

`DELETE http://localhost:3000/holes/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the hole to delete

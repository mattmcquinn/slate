# Courses

## Get all courses

```shell
curl -X GET -H "Authorization: Bearer token"
-H "Content-Type: application/vnd.api+json" "http://localhost:3000/courses"
```

> The above command returns JSON structured like this:

```json
{
  "data": [
    {
      "id": "1",
      "type": "courses",
      "links": {
        "self": "http://localhost:3000/courses/1"
      },
      "attributes": {
        "name": "White-Dach",
        "num-holes": 18
      },
      "relationships": {
        "holes": {
          "links": {
            "self": "http://localhost:3000/courses/1/relationships/holes",
            "related": "http://localhost:3000/courses/1/holes"
          }
        },
        "course": {
          "links": {
            "self": "http://localhost:3000/courses/1/relationships/course",
            "related": "http://localhost:3000/courses/1/course"
          }
        }
      }
    },
    {
      "id": "2",
      "type": "courses",
      "links": {
        "self": "http://localhost:3000/courses/2"
      },
      "attributes": {
        "name": "BerJuan",
        "num-holes": 9
      },
      "relationships": {
        "holes": {
          "links": {
            "self": "http://localhost:3000/courses/2/relationships/holes",
            "related": "http://localhost:3000/courses/2/holes"
          }
        },
        "course": {
          "links": {
            "self": "http://localhost:3000/courses/2/relationships/course",
            "related": "http://localhost:3000/courses/2/course"
          }
        }
      }
    }
  ]
}
```

This endpoint retrieves all courses

### HTTP Request

`GET http://localhost:3000/courses`

## Get a course

```shell
curl -X GET -H "Authorization: Bearer token"
-H "Content-Type: application/vnd.api+json" "http://localhost:3000/courses/1"
```

> The above command returns JSON structured like this:

```json
{
  "data": {
    "id": "1",
    "type": "courses",
    "links": {
      "self": "http://localhost:3000/courses/1"
    },
    "attributes": {
      "name": "White-Dach",
      "num-holes": 18
    },
    "relationships": {
      "holes": {
        "links": {
          "self": "http://localhost:3000/courses/1/relationships/holes",
          "related": "http://localhost:3000/courses/1/holes"
        }
      },
      "course": {
        "links": {
          "self": "http://localhost:3000/courses/1/relationships/course",
          "related": "http://localhost:3000/courses/1/course"
        }
      }
    }
  }
}
```

This endpoint retrieves a course

### HTTP Request

`GET http://localhost:3000/courses/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the course to retrieve


## Create a course

```shell
curl -X POST -H "Authorization: Bearer token" -H "Content-Type: application/vnd.api+json" -d '{
  "data": {
    "type": "courses",
      "attributes": {
        "name": "Schroeder Park",
        "num-holes": 9
      }
  }
}' "http://localhost:3000/courses/"
```

> The above command returns JSON structured like this:

```json
{
  "data": {
    "id": "3",
      "type": "courses",
      "links": {
        "self": "http://localhost:3000/courses/3"
      },
      "attributes": {
        "name": "Schroeder Park",
        "num-holes": 9
      },
      "relationships": {
        "holes": {
          "links": {
            "self": "http://localhost:3000/courses/3/relationships/holes",
            "related": "http://localhost:3000/courses/3/holes"
          }
        },
        "course": {
          "links": {
            "self": "http://localhost:3000/courses/3/relationships/course",
            "related": "http://localhost:3000/courses/3/course"
          }
        }
      }
  }
}
```

This endpoint creates a course

### HTTP Request

`POST http://localhost:3000/courses`

## Update a course

```shell
curl -X PUT -H "Authorization: Bearer token" -H "Content-Type: application/vnd.api+json" -d '{
  "data": {
    "type": "courses",
      "id": 1,
      "attributes": {
        "num-holes": 9
      }
  }
}' "http://localhost:3000/courses/1"
```

> The above command returns JSON structured like this:

```json
{
  "data": {
    "id": "1",
      "type": "courses",
      "links": {
        "self": "http://localhost:3000/courses/1"
      },
      "attributes": {
        "name": "White-Dach",
        "num-holes": 9
      },
      "relationships": {
        "holes": {
          "links": {
            "self": "http://localhost:3000/courses/1/relationships/holes",
            "related": "http://localhost:3000/courses/1/holes"
          }
        },
        "course": {
          "links": {
            "self": "http://localhost:3000/courses/1/relationships/course",
            "related": "http://localhost:3000/courses/1/course"
          }
        }
      }
  }
}
```

This endpoint updates a course

### HTTP Request

`PUT http://localhost:3000/courses/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the course to update

## Delete a course

```shell
curl -X DELETE -H "Authorization: Bearer token"
-H "Content-Type: application/vnd.api+json" "http://localhost:3000/courses/1"
```

> The above command returns 204 No Content

This endpoint deletes a course

### HTTP Request

`DELETE http://localhost:3000/courses/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the course to delete

---
title: API Reference

language_tabs:
  - shell

toc_footers:
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - users
  - courses
  - holes
  - scores
  - errors

search: true
---

# Introduction

Welcome to the DG-Scorecard API! You can use our API to store rounds of disc
golf!

All requests require the Content-Type to be application/vnd.api+json

> To specify the Content-Type, use this code:

```shell
curl "api_endpoint_here"
     -H "Content-Type: application/vnd.api+json"
```

# Authentication

> To authorize, use this code:

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: Bearer token"
```

> Make sure to replace `token` with your [JSON Web Token (JWT)](https://jwt.io).

DG-Scorecard expects the JWT to be included in most API requests to the
server in a header that looks like the following:

`Authorization: Bearer token`

<aside class="notice">
You must replace <code>token</code> with your personal JWT.
</aside>

## Get your JWT

This endpoint responds with your JWT

### HTTP Request

`POST http://localhost:3000/user_token`

> To receive your JWT, use this code:

```shell
curl -X POST -H "Content-Type: application/vnd.api+json"
             -d '{"auth":{"email":"example@email.com","password":"password"}}'
                 "http://localhost:3000/user_token"
```

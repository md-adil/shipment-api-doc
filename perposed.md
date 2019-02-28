## Based on REST API

## Authentication
    <!-- Suggested OAuth2.0 -->
    a very simple implementation
    https://oauth.net/2/ ( help contents )

### ex: Password Grant Tokens
#### Getting token
    POST /oauth/token

#### Request
    {
        "grant_type": "password",
        "username": "email@example.com",
        "password": "my-password"
    }

#### Response ( Success )
    {
        "access_token: "The token",
        "expires_in: 12344 // contains the number of seconds until the access token expires
    }

for now token validity will be lifetime, we will improve later.

#### Response Error ( 422 ) on failure
    {
        "message": "Username or password is not valid"
    }



### Header for Authorized request
    Authorization: Bearer <token>


## Warehouse ( Need but not compulsory )
    GET /warehouses - List All warehouse
    POST /warehouses - Create new warehouse
    PUT /warehouse/<id> - Updating warehouse

## Orders ( Required )
    GET /orders - List All Orders
    POST /orders/create - Creating Order
    PUT /orders/<id> - Updating order

    GET /orders/<id>/track
    PUT /orders/<id>/cancel

    POST /orders/<id>/
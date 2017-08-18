# AdopteUnFillot's REST API

AdopteUnFillot use Laravel 5.4 to provide a REST API.   
The API code is located in `/server/`

!> This API will only reply correctly to a `X-Requested-With: XMLHttpRequest` request with a `Authorization: Bearer <api_token>` Header!

## Getting started

- Clone this repository : `git clone git@github.com:MrWazaby/AdopeUnFillot.git && cd AdopteUnFillot/server`
- Install the dependencies : `composer install && npm install`
- Create a `.env` file based on `.env.example`
- Generate your application key : `php artisan key:generate`
- Install migrations : `php artisan migrate`
- Run the dev server : `php artisan serve`


## User authentification

!> AdopteUnFillot use the default Laravel auth. Please read [the documentation](https://laravel.com/docs/5.4/authentication)  

The first step is to fetch the API token for the session, using this route:  
`GET /api/v1/token`
Using basic auth with email/password.  

The API will return an api_token or an (if auth failed)
``` json
{
    "error": "Invalid credentials."
}
```

?> This route is the only one to be accessible without an api_token

## User API

To get current user data just use this route:  
`GET /api/v1/user`

This will return smothing like that :
``` json
{
    "id": 1,
    "email": "alexandre.martin@efrei.net",
    "created_at": null,
    "updated_at": null,
    "codeEfrei": 20140303,
    "firstNname": "Alexandre",
    "lastName": "Martin",
    "dob": "0018-02-17",
    "api_token": "njvzaBWcKLKToLeWa8pXUrojVxHDPTAdrRWdNuEsKPo7OCFNBF5eIxyulo9n",
    "promo": "2019",
    "sex": 1,
    "majeur": "Sécu",
    "school": "Efrei",
    "isGodFather": 0
}
```

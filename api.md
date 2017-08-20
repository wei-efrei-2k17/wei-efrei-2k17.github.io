# AdopteUnFillot's REST API

AdopteUnFillot use Laravel 5.4 to provide a REST API.   
The API code is located in `/server/`

!> This API will only reply correctly to a `X-Requested-With: XMLHttpRequest` request with a `Authorization: Bearer <api_token>` Header! Otherwise you may recive an `{"error":"Unauthenticated."}` response.

!> AdopteUnFillot use the default Laravel auth. Please read [the documentation](https://laravel.com/docs/5.4/authentication)  

## Getting started

- Clone this repository : `git clone git@github.com:MrWazaby/AdopeUnFillot.git && cd AdopteUnFillot/server`
- Install the dependencies : `composer install && npm install`
- Create a `.env` file based on `.env.example`
- Generate your application key : `php artisan key:generate`
- Install migrations : `php artisan migrate`
- Run the dev server : `php artisan serve`

## Token API

### [GET] Get Token

The first step is to fetch the API token for the session, using this route:  
`GET /api/v1/token`
Using basic auth with email/password.  

The API will return an api_token or an (if auth failed)
``` json
{
    "error": "Invalid credentials."
}
```

?> This route is accessible without an api_token

## User API

### [GET] Get User

To get current user data just use this route:  
`GET /api/v1/user`

This will return smothing like that:
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

### [GET] Get Registration Variables

To get the variable for the registration form use this route:  
`GET /api/v1/user/create`

This will return smothing like that:
``` json
{
    "promos": [
        "2018",
        "2019",
        "2020",
        "2021",
        "2022"
    ],
    "schools": [
        "Efrei",
        "Esigetel",
        "Efreitech"
    ],
    "majeurs": [
        "Aucune",
        "Buisness Intelligence",
        "System and Cloud Engineering",
        "Image et Réalité Virtuelle",
        "Big Data",
        "Information Technology for Finance",
        "Sécurité",
        "Software Engineering",
        "Bio-Informatique",
        "Avionique et Espace",
        "Droïde et Drones",
        "Network and Virtualisation",
        "Energies nouvelles et Réseaux intelligents"
    ]
}
```

?> This route is accessible without an api_token, you can edit variables in `server/app/Http/Controllers/UserController.php`

### [POST] Create User

To create a new user use the route:
`POST /api/v1/user`

This will return you:
`{"success":true}`
Or an error message.

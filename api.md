# AdopteUnFillot's REST API

AdopteUnFillot use Laravel 5.4 to provide a REST API.   
The API code is located in `/server/`

## Getting started

- Clone this repository : `git clone git@github.com:MrWazaby/AdopeUnFillot.git && cd AdopteUnFillot/server`
- Install the dependencies : `composer install && npm install`
- Create a `.env` file based on `.env.example`
- Generate your application key : `php artisan key:generate`
- Install migrations : `php artisan migrate`
- Run the dev server : `php artisan serve`


## User authentification

!> AdopteUnFillot use different auth for administration and the app! Admin use the default Laravel auth and the app use a custom auth, Please read the different carefully.

?> *TODO* write this section 

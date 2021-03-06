# AdopteUnFillot's Web App

AdopteUnFillot use VueJS 2 to provide a Web App and the UI Kit [Now-UI](http://demos.creative-tim.com/now-ui-kit/index.html?affiliate_id=97705#pablo).   
The Web App code is located in `/client/`

?> AdopteUnFillot Web App use Axios to interact with the REST API. [Learn more](https://github.com/mzabriskie/axios)

!> AdopteUnFillot Web App use [ESLint standard](https://github.com/feross/standard/blob/master/RULES.md#javascript-standard-style)

## Getting started

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report

# run unit tests
npm run unit

# run e2e tests
npm run e2e

# run all tests
npm test
```

For detailed explanation on how things work, checkout the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).

## Results

There is a `window.blockApp` variable located in the `main.js`. If this variable is set to true the app will block registrations and change the hub page with the result page.

The result page is located in `client/src/components/results`.

## Landing page

The landing page is composed with the login page, the registration page.

You can find VueJS components for the landing section in `client/src/components/landing`

!> The password reset page is handeled by Laravel, if you have time, you may want to integrete it to the VueJS app.

### Login

The login is a basic component, nothing realy complicated here. Just read the code.

### Registration

Idem for the registration component

## App components

This is the app components (Discover/likes/matches).
Components are located in `client/src/components`

I have added a now-ui function, this function is call when components is mounted, it's use to initialize Now UI JavaScript.

### Improvements

You may want to improve the following :
- Show tastes on the same tab (with the picture and the like button)
- Allow user to see profil of his likes/matches
- Stick the footer to bottom with flexboxs
- Improve mobile version

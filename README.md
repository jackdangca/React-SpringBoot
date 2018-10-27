# React-SpringBoot

<p align="center">
    <a href="http://movie.zzhpro.com">
        <img src="./src/main/resources/static/favicon.ico" width="152">
    </a>
    <h3 align="center">Movie Helper</h3>
    <p align="center">
        <a href="https://github.com/zzh1991/React-SpringBoot/blob/master/LICENSE"><img src="https://img.shields.io/github/license/zzh1991/React-SpringBoot.svg"></a>
        <a href="#"><img src="https://img.shields.io/github/languages/top/zzh1991/React-SpringBoot.svg"></a>
        <a href="#"><img src="https://img.shields.io/github/languages/count/zzh1991/React-SpringBoot.svg"></a>
        <a href="#"><img src="https://img.shields.io/github/search/zzh1991/React-SpringBoot/goto.svg"></a>
        <a href="https://github.com/zzh1991/React-SpringBoot/blob/master/.travis.yml"><img src="https://img.shields.io/travis/zzh1991/React-SpringBoot/master.svg"></a>
    </p>
    <p align="center">
        Movie management and find valueable movies to watch<br>
    </p>
</p>

## Install
- install node dependencies: `npm install` or `yarn` 
- configure you database name (an empty database) in application.properties
    - your PostgreSQL database configuration
- prepare front static files
    - dev mode
        - `yarn start` or `npm start`
    - build mode
        - `yarn run deploy` or `npm run deploy`
- start the web app in IDE
- open browser
    - `build mode`: go to http://localhost:8080
    - `dev mode`: go to http://localhost:3000

## Demo: [Movie Helper](http://movie.zzhpro.com)
### Recent Movies
![Recent](./pictures/recent-movie.png)
### Top 100 Movies
![Top](./pictures/top-movie.png)
### Viewed Movies
![View](./pictures/view-movie.png)
### Stared Movies(Want to watch)
![Star](./pictures/star-movie.png)
### All Movies
![All](./pictures/all-movie.png)

### Reference
- [recent movies](https://movie.douban.com/)
- [top movies](https://movie.douban.com/top250?start=0&filter=)

## TO DO LIST
### login page
    - [x] sign in / sign up (removed)
### data bind with user id

### improvement
    - [x] sync recent / top movies
    - [x] upgrade to antd 3.10.1
    - [x] latest sync time
    - [x] search movie name
    - [x] database / layout re-dsign
    - [x] schedule task 

## Dependency
### front-end
- react
- redux
- react-router-dom
- react-redux
- redux-thunk
- redux-saga
- [ant design](https://ant.design)
- day.js
- webpack 3
- babel dependency
- eslint dependency

### backend
- Spring Boot 2
- PostgreSQL
- Guava
- Swagger2
- Flyway
- Prometheus

## Config
### hot deploy for Intellij IDEA
```xml
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-devtools</artifactId>
    <optional>true</optional>
</dependency>
```
- setting -> compiler -> make project automatically
- ctrl + shift + a -> registry -> auto make enabled

## react router v4
### HashRouter
- install react-router-dom
```javascript
<HashHashRouter>
  <div>
    <Route exact path="/" component={App} />
    <Route path="/app" component={App} />
  </div>
</HashRouter>

// this.context.router.history.push('path');
```

## Problems
### Migrate flyway 3.x to 5.x issue
> firstly should migrate to **4.2.0** and then 5.x

## Package front files
### webpack
#### babel
- arrow function: transform-class-properties
- async: "transform-runtime", { "polyfill": false, "regenerator": true }

### [Parcel](https://parceljs.org/)
#### Problems
- css packaged, class name is not same, so not css effect
- svg, jpg url path is not right for static resource, not web resource

# Beer API

## Getting Started

A poorman's Beer Advocate. See [Usage](#usage) for sample cURL commands below.

## Highlights

* Rails 5 REST API
* JWT Authentication
* JSON:API format

### Prerequisites

Install Rails API dependencies:

```
$ bundle install
```

Setup the development environment:

```
$ bin/rails db:setup
```

Run the specs:

```
$ bin/rspec spec
```


### Installing

Give it a go!

```
$ bin/rails s
```

## Usage

### Get get a JWT

```
curl -X POST \
  http://localhost:3000/api/v1/auth \
  -H 'Cache-Control: no-cache' \
  -H 'Content-Type: application/json' \
  -d '{ "data": { "attributes": { "email":"user@foo.com", "password":"password" }} }'
```

### Create a beer

```
curl -X POST \
  http://localhost:3000/api/v1/beers \
  -H 'Cache-Control: no-cache' \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Token token={{JWT_TOKEN}}' \
  -d '{"data":{ "attributes":{ "name": "Your Awesome Beer!!","style":"Awesome Ale","yeast":"1097 - Fidy Ten","hop":"Blue Dream","malts":"Black malt","ibu":"66 IBU","alcohol":"8.9%","blg":"14.0°Blg"}}}'
```

### Get a list of beers

```
curl -X GET \
  http://localhost:3000/api/v1/beers \
  -H 'Authorization: Token token={{JWT_TOKEN}}' \
  -H 'Cache-Control: no-cache'
```

### Get data for one beer

```
curl -X GET \
  http://localhost:3000/api/v1/beers/1 \
  -H 'Authorization: Token token={{JWT_TOKEN}}' \
  -H 'Cache-Control: no-cache'
```

## Built With

* [Rails 5 API](https://rubyonrails.org/) - Rail 5 API framework
* [SQLite](https://www.sqlite.org/) - Stock Rails database

# Superheroes API

## Entity Relational Diagram


<img width="1012" alt="domain" src="https://user-images.githubusercontent.com/105637783/227791193-4364e4f3-4666-4b5c-87ea-b1d5b1e416d9.png">




### Endpoints

| index           |      show            |      create     |
|-----------------|:--------------------:|----------------:|
| {{host}}/heroes |  {{host}}/heroes/:id | {{host}}/heroes |
| {{host}}/powers |  {{host}}/powers/:id | {{host}}/powers |
| {{host}}/hero-powers |  {{host}}/hero-powers/:id | {{host}}/hero-powers |

### Ruby Version

2.4.7

### First time set up

1. Clone the code from GitHub using `git clone https://github.com/jwillie-26/Superheroes-API.git`
2. Read this README ;
3. Install dependencies using `bundle`.
4. Seeding test data-rails db:seed to seed the data.
5. Turn on the server with `rails s`- The server will run on `http://localhost:3000`

.....................................................................

Install the dependencies and start the server.

```sh
bundle install
```

Migrate into the database and seed with provisioned fake data...

```sh
rails db:migrate db:seed
```

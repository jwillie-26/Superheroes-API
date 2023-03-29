# Superheroes API



## Ruby version
version: 2.7.4 or newer!

## Requirements


Create a Rails API backend. Have at least three resources (three DB tables).

## MODEL Deliverables and Relationships
Create the following relationships:

- A `Hero` has many `Power`s through `HeroPower`
- A `Power` has many `Hero`s through `HeroPower`
- A `HeroPower` belongs to a `Hero` and belongs to a `Power`

![](/assets/superheroes.png)


## Deployment Link
This link can be easily used to test the different routes/requests available to the API server. If you want to have the project in your development environment, proceed to set it up as outlined in the section that follows.

```bash
https://superheroes-api-apvb.onrender.com
```

## Setup
In order to use this repository, you need the following:
* Operating System (Windows 10+, Linux 3.8+, or MacOS X 10.7+)
* An account on Postman API Platform. CLICK HERE TO CREATE ONE
* RAM >= 4GB
* Free Space >= 2GB

1. Fork and clone the repository.
2. Ensure the ruby gems are setup in your machine
```
bundle install
```
3. Perform any pending database migrations and seed data
```
rails db:migrate db:seed
```
4. Make sure no other application is using PORT 3000 and run the application
```
rails s
```
5. Using your preferred API testing platform (Postman, ThunderClient, etc), proceed to test the various routes available to the API. This will be your base URL:
```
http://localhost:3000
```
## validations Deliverables
Add validations to the `HeroPower` model:

- `strength` must be one of the following values: 'Strong', 'Weak', 'Average'

Add validations to the `Power` model:

- `description` must be present and at least 20 characters long

## Routes
Set up the following routes. Make sure to return JSON data in the format
specified along with the appropriate HTTP verb. Also, ensure that errors are returned and handled appropriately. This includes and is not limited to necessary status codes.

```
GET /heroes
```

Return JSON data in the format below:

```
[  

{ "id": 1, "name": "Kamala Khan", "super_name": "Ms. Marvel" },  

{ "id": 2, "name": "Doreen Green", "super_name": "Squirrel Girl" },  

{ "id": 3, "name": "Gwen Stacy", "super_name": "Spider-Gwen" }

]
```

```
GET /heroes/:id
```

If the `Hero` exists, return JSON data in the format below:

```
{
  "id": 1,
  "name": "Kamala Khan",
  "super_name": "Ms. Marvel",
  "powers": [
    {
      "id": 1,
      "name": "super strength",
      "description": "gives the wielder super-human strengths"
    },
    {
      "id": 2,
      "name": "flight",
      "description": "gives the wielder the ability to fly through the skies at supersonic speed"
    }
  ]
}
```


If the `Hero` does not exist, return the following JSON data, along with
the appropriate HTTP status code:

```
{   "error": "Hero not found" }
```

```
GET /powers
```

Return JSON data in the format below:

```
[
  {
    "id": 1,
    "name": "super strength",
    "description": "gives the wielder super-human strengths"
  },
  {
    "id": 1,
    "name": "flight",
    "description": "gives the wielder the ability to fly through the skies at supersonic speed"
  }
]
```

```
 GET /powers/:id
```
If the `Power` exists, return JSON data in the format below:

```
{
  "id": 1,
  "name": "super strength",
  "description": "gives the wielder super-human strengths"
}
```

If the `Power` does not exist, return the following JSON data, along with
the appropriate HTTP status code:

```
{
  "error": "Power not found"
}
```

```
PATCH /powers/:id
```
This route should update an existing `Power`. It should accept an object with
the following properties in the body of the request:

```
{
  "description": "Updated description successfully."
}
```

If the `Power` exists and is updated successfully (passes validations), update
its description and return JSON data in the format below:

```
{
  "id": 1,
  "name": "super strength",
  "description": "Updated description"
}
```

If the `Power` does not exist, return the following JSON data, along with
the appropriate HTTP status code:

```
{
  "error": "Power not found"
}
```

If the `Power` is **not** updated successfully (does not pass validations),
return the following JSON data, along with the appropriate HTTP status code:

```
{
  "errors": ["validation errors"]
}
```

```
POST /hero_powers
```
This route should create a new `HeroPower` that is associated with an
existing `Power` and `Hero`. It should accept an object with the following
properties in the body of the request:

```
{
  "strength": "Average",
  "power_id": 1,
  "hero_id": 3
}
```

If the `HeroPower` is created successfully, send back a response with the data
related to the `Hero`:

```
{
  "id": 1,
  "name": "Kamala Khan",
  "super_name": "Ms. Marvel",
  "powers": [
    {
      "id": 1,
      "name": "super strength",
      "description": "gives the wielder super-human strengths"
    },
    {
      "id": 2,
      "name": "flight",
      "description": "gives the wielder the ability to fly through the skies at supersonic speed"
    }
  ]
}
```

If the `HeroPower` is **not** created successfully, return the following
JSON data, along with the appropriate HTTP status code:

```
{
  "errors": ["validation errors"]
}
```

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






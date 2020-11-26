--- Techreads coursework ---

-- basic c# net.core API for books SPA project that works with MongoDB --


In case that you like to work with actual database (rather than what has been given as an "API" in the coursework material), 
this is a basic implemantation of and API in written in c#/.net core (.NET Core SDK 3.0 or later).

This includes a controller with casic CRUD implemented.


To use this:

1. **clone repo (and restore once open)**

2. **Make sure you have MongoDB installed**
  - create database: use BookstoreDb
  - create collection: db.createCollection('Books')
  - use the command inside "BooksApi/MongoDb/insertSampleBooks.json" file to insert sample data to DB
  
3. **run the API:** dotnet run

4. **Test:** use GET request in Postman on your localhost, example: http://localhost:5000/api/books
This will return list of books:

  ![alt text](https://i.ibb.co/RNpqfqn/Screenshot-from-2020-11-26-08-13-58.png)







**Sample book collection structure:**

```javascript
{
        "book_id": "1",
        "authors": ["David Flanagan"], 
        "title": "JavaScript:The Definitive Guide, 7th Edition", 
        "description": "JavaScript is the programming language of the web....",
        "publisher": "O'Reilly", 
        "year": "2020",
        "isbn": "978-1491952023",
        "book_category": "JavaScript",
        "ratings": [5,4],
        "reviews" : [
            {"reviewer":"anon1", "review": "Great book, very comprehensive"},
            {"reviewer":"anon2", "review": "Tells you everything you need to know about JavaScript"},
        ]
    }
```


CRUD:

**Get all books: use GET on:** 

``` http://localhost:5000/api/books/ ```

Returns: 200 OK


**To update (takes "id" and Book object): use PUT on:** 

``` http://localhost:{port number}/api/books/{object id}```

for example:

``` http://localhost:5000/api/books/5fbf85d14a55652495b351ef ```

and JSON object in body, for example:

```javascript
{
        "_id": "5fbf85d14a55652495b351ef"
        "book_id": "1",
        "authors": ["New Author"], 
        "title": "New Updated Titel...", 
        "description": "New description...",
        "publisher": "New Publisher ... and so on", 
        "year": "2020",
        "isbn": "978-1491952023",
        "book_category": "JavaScript",
        "ratings": [5,4],
        "reviews" : [
            {"reviewer":"anon1", "review": "Great book, very comprehensive"},
            {"reviewer":"anon2", "review": "Tells you everything you need to know about JavaScript"},
        ]
 }

```

successful update returens: 204 No content



**To create new record: use POST on:** 

```http://localhost:5000/api/books/```

With JSON in the body, for example:
```javascript
{
    "book_id": "7",
    "authors": [
        "Name Surname"
    ],
    "title": "New Book",
    "description": "New Book description....",
    "publisher": "New publisher",
    "year": "2020",
    "isbn": "978-1838346535",
    "book_category": "New-category",
    "price": 23,
    "ratings": [],
    "reviews": [
        {
            
        }
    ]
```
succesful create returns: 201 Created



**To delete: use DELETE on:** 

```http://localhost:{port number}/api/books/{object id}```

for example:

```http://localhost:5000/api/books/5fbf85d14a55652495b351ef```



have fun...

# techreads
basic c# net.core API for books SPA project that works with MongoDB


In case you like to work with actuall database this is a basic implemantation of and API in c#/.net core
with MongoDB and a controller with casic CRUD.

To use this:

1. clone repo (and restore once open)
2. Make sure you have MongoDB installed
  - create database: use BookstoreDb
  - create collection: db.createCollection('Books')
  - use the command inside "BooksApi/MongoDb/insertSampleBooks.json" file to insert sample data to DB
  
3. run the API: dotnet run
4. Test: use GET request in Postman on your localhost, example: http://localhost:5000/api/books
This will return list of books:

  ![alt text](https://i.ibb.co/RNpqfqn/Screenshot-from-2020-11-26-08-13-58.png)

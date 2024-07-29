## install mongo db, and mongo db shell

#### Enter Mongo Shell:
```
    mongosh
    help # will show all available commands
```
#### exit Mongo Shell:
```
    exit
```
#### Show all database:
```
    show dbs
```
#### clear shell
```
    cls
```
#### Use any database. before running command for a databases use this command:
```
   use <database_name> 
```
#### See which database we are currently using:
```
    db
```
#### Show all collections in a database
```
    use <database_name> # if you are already on the db then no need 

    show collections
```

#### we can create and use a variable in the shell:  
```
    var name = 'string' # here 'name' is the variable_name and 'string' is the value.
    name # will show the value of 'name'

    name = 'change_string' # will change the value of the string 
```

#### Insert one new document/ obj in mongodb collection
```
# Lets say we have a data base named 'bookstore' and a collection 'books'
# fields-> title, author, pages, rating, genres

db.books    # this is to check that there is no error. or check is current db has the 'books' collection. this should return "bookstore.books"

db.books.insertOne({title: "string", author: "string", pages: 300, rating:7, genres=["1str","2str"]}) 
# return-> {
#   acknowledged: true
#   insertedId: ObjectId("4123423525faf11414wsdfr2")   
# }

```

`
Note: if we tries to insert data in a collection which doesn't exist then this command will create  the collection and insert into it.
`

#### Insert many new documents/ objs in mongodb collection
```
# Lets say we have a data base named 'bookstore' and a collection 'books'
# fields-> title, author, pages, rating, genres

db.books    # this is to check that there is no error. or check is current db has the 'books' collection. this should return "bookstore.books"

db.books.insertMany([
    {
        title: "string", author: "string", pages: 300, rating:7, genres=["1str","2str"]
    },
    {
        title: "string", author: "string", pages: 300, rating:7, genres=["1str","2str"]
    },
    {
        title: "string", author: "string", pages: 300, rating:7, genres=["1str","2str"]
    },
]) 

# return-> {
#   acknowledged: true
#   insertedIds: {
#        '0': ObjectId("4123423525faf11414wsdfr2"),
#        '1': ObjectId("5153423525f3a34414wsd234")
#    }
# }
```

`
Note: if we tries to insert data in a collection which doesn't exist then this command will create  the collection and insert into it.
`

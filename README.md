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

#### get all documents from collection
```
db.collection_name.find() # in mongo shell we will see only 20 documnet but in code base we will get all the documents

# in mongo shell if we want to see more document then write 'it' in the shell and enter
# it means itaration
```

#### get document, find document with options
```
# commands 
db.collaction_name.find({filter query},{which fields you want},{options}) 
```

```
################### Providing only first argument for filter. returns whole object That matchs the fields with values. ####################

db.collection_name.find({fild_name: 'match_value'}) 
db.collection_name.find({fild_name1: 'match_value1', fild_name2: 'match_value2'}) # will match both 

################### Providing first and 2nd argument for filter and specifiying which fields we want ######################
db.collection_name.find({fild_name: 'match_value'}, {title: 1, author: 1})  # will return the objs that matchs the filters, only title and author values.
db.collection_name.find({fild_name1: 'match_value1', fild_name2: 'match_value2'}, {title: 1, author: 1})  # will return the objs that matchs the filters, only title and author values. 
```


#### get/find one document
```
db.books.findOne({ _id: ObjectId("your_specific_id") }) #search with id 
```

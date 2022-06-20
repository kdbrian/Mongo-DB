1.Start
    To start
        windows win+r-->opens cmd
        type in mongosh-->opens mongo commandline Tool(CLI)

2.View Db
    To view existing databases
        ~show dbs

3.Select db
    To select a database
        ~ use <replace with the name of the database>

4.Show collections
    To show existing collections in current db
        ~ show collections
<!-- Create -->
5.Create new Database
    To create a new database
        ~use<database name>
4.Insert a document in current Db 
    To insert a document/create a new collection
        ~db.<collection-name>.insertOne({<document in json format>})
            # a unique id will always be created for new documents

4.Insert many document in current Db 
    To insert many documents
        ~db.<collection-name>.insertManY({<documents in json format>})
            #unique ids will be created for each document
<!-- Query -->
5.View all document in current db
    To view all documents
        ~db.<collection-name>.find()

6.To get a single document from current db
    To get a single document based on a filter i.e. name, id, rating
        ~db.<collection-name>.find({filter in Js Object format e.g. name:"brian" })

6.To get a single document from current db and return certain/specific field
    To get a single document based on a filter i.e. name, id, rating
        ~db.<collection-name>.find({filter in Js Object format e.g. name:"brian" },{fields to be returned are marked equal to one e.g. name:1,age:1})

7.Using the greater than operator
    To select all documents for example with a rating of greater than 5
        ~db.<collection-name>.find({filter in Js Object format e.g. rating:{$gt:5}})

7.1.Using the greater than or equal to operator
    To select all documents for example with a rating >= 5
        ~db.<collection-name>.find({filter in Js Object format e.g. rating:{$gte:5}})

8.Using the less than operator
    To select all documents for example with a rating of less than 5
        ~db.<collection-name>.find({filter in Js Object format e.g. rating:{$lt:5}})

8.1.Using the less than or equal to operator
    To select all documents for example with a rating <= 5
        ~db.<collection-name>.find({filter in Js Object format e.g. rating:{$lte:5}})

9.Using the or Operator $or
    To select documents that match either filter e.g rating greater than 5 or price greater than 400
        ~db.<collection-name>.find({$or:[array of filter objects e.g. {price:{$gte:400}},{rating:{$gte:5}}]})
        fetchs all documents with either a rating >=5 or a price >= 400

10.Operation similar to logical and(&&)
    To select documents that match either filter e.g rating greater than 5 or price greater than 400
        ~db.<collection-name>.find({filter objects e.g. price:{$gte:400},rating:{$gte:5}})
        fetchs all documents with a rating >=5 and a price >= 400

11.updating a single document($set operator)
        ~db.<collection-name>.updateOne({filter in Js Object format e.g. _id=ObjectId("62ad7d2d0df509ebcdfd0c90")},{details to be updated e.g. {$set:{ price: 200}}});

            #if query matches multiple documents only the first one will be updated
            #use uniques fields in filter for example Id,name
            #if a new field is added in the $set operator the fields will be created

12.updating Many documents($set operator)
        ~db.<collection-name>.updateOne({filter in Js Object format e.g. authour:"Brian"},details to be updated e.g. {$set:{ price: 200,rating:7}});

            #if query matches multiple documents all will be updated
            #use uniques fields in filter for example Id,name
            #if a new field is added in the $set operator the fields will be created

13.Replacing a single/documents($set operator)
        ~db.<collection-name>.updateOne({filter in Js Object format e.g. _id=ObjectId("62ad7d2d0df509ebcdfd0c90")},{details to be updated e.g. {new document/documents in JS object format}});

            #if query matches multiple documents all will be replaced
            #use uniques fields in filter for example Id,name
            #if a new field is added in the $set operator the fields will be created

14.Deleting a single document in current db
    To delete a documents
        ~db.<collection-name>.deleteOne({filter in Js Object format e.g. name:"brian" })

15.To delete many documents current db
    To delete documents based on a filter i.e. name, id, rating
        ~db.<collection-name>.deleteMany({filter in Js Object format e.g. name:"brian" })

16.To delete all documents current db
    To delete documents based on a filter i.e. name, id, rating
        ~db.<collection-name>.deleteMany({no filter is passed})
        
        #Not advisable⚡💀


.the and operator

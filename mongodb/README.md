# Topics covered in this webpage are mentioned below

- CRUD in MongoDB

    - Create
    - Read
    - Update
    - Delete
- Queries
- Aggrigation

==========================================================================
# 1. Database Commands
### View all databases
    show dbs
### Create a new or switch databases 
    use dbName
### View current Database
    db
### Delete Database 
    db.dropDatabase()

# 2. Collection Commands (Create)
### Show Collections
    show collections
### Create a collection named 'comments'
    db.createCollection('comments')
### Create a collection named 'person'
some of the queries will be performed on this person collection 

    db.createCollection("person")
### Drop a collection named 'comments'
    db.comments.drop()

# 3. Insert Commands  
    - insert     : insert many or one document
    - insertOne  : insert only one document
    - insertMany : insert many Documents

substitute above 3 based on your data in place of "method" in below syntax
 
    db.<collection_name>.method(<Object> or <Array  of Objects>)​
                         
### Insert One Row
    db.comments.insert({
        'name': 'Harry',
        'lang':  'JavaScript',
        'member_since': 5
     })

###  Insert many Rows
    db.comments.insertMany([    
        {
        'name': 'Harry',
        'lang': 'JavaScript',
        'member_since': 5
        }, 

        {'name': 'Rohan',
        'lang': 'Python',
        'member_since': 3
        },

        {'name': 'Lovish',
        'lang': 'Java',
        'member_since': 4
        }])
### Insert many rows from persons.json file
     db.person.insert( 
     
         <!-- paste all the content from persons.json file -->
     )
# 4. Row(Document) Commands [Read]
It is simillar to select command of SQL

    find    : to select multiple Documents
    findOne : to select only one document 
<!-- (if no condition or condition is given then 1st 
occurance document will be shown) -->

###  Show all Rows in a Collection named "comments" and "person" 
    db.comments.find()
    db.person.find({})
### Show all Rows in a Collection (Prettified)
    db.comments.find().pretty()
### Find the first row matching the object
    db.person.findOne({name: 'Kishan'})
### Show all rows in a Collection with given condition
    db.person.find(
        {"gender" : "female" ,
         "eyeColor" : "blue"}
         ​​)

### Search in a MongoDb Database
    db.comments.find({lang:'Python'})
### Limit the number of rows in output
    db.comments.find().limit(2)
### Count the number of rows in the output
    db.comments.find().count()

# 5. Update Commands

 1) update()
 2) updateOne()
 3) updateMany()
 4) replaceOne()

update syntax:-

update({  },{  },{  })
      
      db.<collection_name>.method(<query>,<update>,<option>)
   
method==> 1,2,3 from above mentioned 

    <query> ==> to find particular document from collection
    <update> ==> we use $set and other operation for modification.
example:-

    db.shoppingCart.update(​
    // below is the <query> to selectthe particulardocument
         { index: 4 },
    // below is the update query we want to write
    // it can have $set, $unset, $inc, $currentDate,$rename ​
         {​
           $set: {​
                cartId: NumberInt(435), 
                 "customer.name": "Samanta Larsen",
                "customer.email": "slarsen@test.com"​
                 },​
           $unset: {​
                newOrder: 1​
                 }​
         }
        //  ​<optional> 
        // {multi:true}
         )​

### Update a row
    db.comments.update(  {name: 'Shubham'},
                        {'name': 'Harry',
                         'lang': 'JavaScript',
                         'member_since': 51}, 
                        {upsert: true}
                     )
###  Mongodb Increment Operator
    db.comments.update({name: 'Rohan'},
                       {$inc:{
                             member_since: 2
                       }})

### Mongodb Rename Operator
    db.comments.update(  {name: 'Rohan'},
                         {$rename:{
                                  member_since:'member'
                        }})
# 6. Delete

## (i) Delete Documents

remove() :- remove will delete all Documents in the collection which are match

    db.<collection>.remove(<query>)

deleteOne()

    db.<collection>.deleteOne(<query>)
deleteMany()

    db.<collection>.deleteMany(<query>)

## (ii) Delete Collections (table)
delete collection with all Documents and indexes

drop()

    db.<collection>.drop()
## (iii) Delete Databases​
delete DB with all collection and Documents

dropDatabase()

when we try to delete database 1st thing to keep in mind is to check what DB we are using then only perform this operation.

    use dbName
    db.dropDatabase()

###  Delete Row 
    db.comments.remove({name: 'Harry'})
# 7. Queries
####  Less than/Greater than/ Less than or Eq/Greater than or Eq
    db.comments.find( {member_since: {$lt:  90} } )
    db.comments.find( {member_since: {$lte: 90} } )
    db.comments.find( {member_since: {$gt:  90} } )
    db.comments.find( {member_since: {$gte: 90} } )

#### Display all the persons detail who are 38 years old 
    db.person.find({age:38})
#### Display all the detail of  the person “Kitty Snow”. 
    db.persons.find({name:"Kitty Snow"})
#### Display all the female details whose eyeColor is blue 
    db.person.find({gender:"female"},{eyeColor:"blue"})
####  Display all persons who don’t like apple 
    db.persons.find({"favoriteFruit" :{$ne:"apple"}})
#### Display all the person documents aged More than 25 
    db.persons.find({age:{$gt :25}})
#### Give the details of only those persons having eye color either “blue” or “green” 
    db.persons.find({eyeColor:{$in:["blue","green"]}})
####   Display all the documents where the age lies between 23 and 27.  Note : 23 &27 excluded. 
    db.person.find({age:{$gt:23,$lt:27}})
#### Using $nin operator retrieve the details of all the person     documents who don’t like banana and apple 
    db.person.find({"favoriteFruit":{$in:["banana","apple"]}})
    
####  Using explicit $and operator retrieve all the male documents aged over 25  O/P : 342 records 
    db.person.find({$and:[{gender:"female"},{eyeColor:{"$eq":"blue"}}]})
####    "$and" & "," are different
    db.persons.find({$and: [ {"age": {"$ne": 25}} , {"age": {"$gte": 20}} ]})

    db.persons.find({"age": {"$ne": 25} , "age": {"$gte": 20}})
#### Display the List of all the male persons or any body over 27 years of age irrespective of the gender using $or operator 
    db.persons.find({$or:[{gender:"male"} , {age: {$gt: 27}}]})
####  Find all the persons who are younger than 24 or like bananas or color of the eyes is either blue or green 

    db.person.find({$or:[{favouriteFruit:"banana"} ,{eyeColor:{$in:["green","blue"]}},{age: {$lt: 27
    
#### Find all the documents having an element “ad” 
    db.person.find({tags:"ad"})
#### Find all the documents where the leading element is “ad” 
    db.person.find({"tags.0":"ad"})
#### Find all the documents with exactly  3 elements 
    db.person.find({tags:{$size:3}})
#### Find all the persons with the second tag “ad” and where tags array consists of exactly 3 tags 
    db.persons.find({$and:[{"tags.2":"ad"},{"tags":{$size:3}}]})
 
 
#### some other commands
    db.person.find({friends: {$elemMatch:{name: "Bob", registered: false }}})

    db.persons.find({friends:{$elemMatch:{registered: false, age: 25 }}})
#### Display all the documents which contains the field “tags”
    db.persons.find({tags:{$exists:true}})
####  Display only those documents which does not contain the field “name”
    db.person.find({name:{$exists:true}})
#### Retrieve all the documents containing index field of int type and having a value 5. 
    db.persons.find({index:{$type:"int",$eq:5}})
#### Perform the following task : 

   - Find all the persons with blue eyes 
   - Return only certain field as shown below 
   - Totally 333 persons must match. 

    db.persons.find({eyeColor:"blue"},{name:"string",age:2,eyeColor:1,_id:0})
     
 
 
# 8. Aggrigation
 
 coming soon















=========================================================================


- For making notes i have taken some information from following website
   - <a href="https://www.codewithharry.com/blogpost/mongodb-cheatsheet">CodeWithHarry</a>
   - Google  
        - https://riptutorial.com/Download/mongodb.pdf
        - https://www.guru99.com/pdf/mongodb_preview.pdf
        - https://www.mongodb.com/developer/quickstart/cheat-sheet/#table-of-contents
        - 

   - linkedin
   -  <a href="https://cheatography.com/tag/mongodb/" target="_blank">Cheatography</a> 
<!-- For mongodb i would recommend you youtube playlist of bucky robert. (Thenewboston) -->


#### if you find any mistakes please let me know so i can modify it.

THANK YOU 

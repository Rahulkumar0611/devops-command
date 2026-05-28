This command lets you enter inside the running Docker container named school_mongo.

docker exec -it school_mongo bash



mongosh

show dbs
show collections
db.users.find()
db.users.find().pretty()

exit


Indexing 
db.classes.getIndexes()

Use the index name:
db.classes.dropIndex("className_1")

db.classes.dropIndexes()

db.classes.getIndexes()

Note:- 
Removing indexes can slow queries.
If you remove a unique index, duplicate data can be inserted afterward.
In production, deleting indexes on huge collections can temporarily affect performance.

writeCode

Write code to:-

- create a database named `sports`.
  use sports
- list all databases present in local mongod server.
  show dbs
- create 3 collections named `cricket`, `football`, `TT` in sports databse.
  var collectionList = ['cricket','football','TT'];
  collectionList.forEach((collectionName)=> {db.createCollection(collectionName)})

- add multiple players in those collections which should have fields like `name`, `age` and `email` and `bid_price`.

db.userData.insertMany(group)

- list all collections in sports database.
  show collections
- rename `TT` collection to `tennis`.
  db.TT.renameCollection("tennis")

- create a capped collection called `khokho` which should have max 3 documents.
  db.createCollection("khokho", { capped : true, size : 1024, max : 3 } )

  Try inserting more than 3 and see what happens?
  when we insert more than the limit /three , the early first one will be removed automatically.

- check whether a collection is capped or not?
  db.khokho.isCapped()
- drop all documents from `football` collection.
  db.football.remove({})
- delete cricket collection completely.
  db.football.drop()
- delete sports database.
  db.dropDatabase()
- check which database you are connected to ?
  db
- connect to test database
  use test

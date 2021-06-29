writeCode

Write command to

- List collections from a database.
  show dbs
- create a new collection in your country database which you created recently.
  use india --> to create the database
  db.createCollection("delhi") --> to create the collection named 'delhi'
  Write code to:-

- crate a database named `weather`
  use weather
- create a capped collection named `temperature` with maximum of 3 documents and try inserting more than 3 to see the result.
  db.createCollection("temperature",{capped:true,size:3,max:3})

db.temperature.insert({"location":"mandapeta"})

db.temperature.insert({"time":"night"})

db.temperature.insert({"status":"good"})

db.temperature.insert({"response":"ok"})

- create a simple collection named `humidity`
  db.createCollection("temperature")
- check whether `temperature` collection is capped or not ?
  db.temperature.isCapped()
- Delete `humidity` collection and then the entire database(weather).
  db.humidity.drop()
  db.dropDatabase()

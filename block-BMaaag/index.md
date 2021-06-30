writeCode

Write code to:-

- create a database named `mountains`
- a collection inside that database named `himalayas`
- insert 1 document into that collection `{name: 'Dhauldhar range', height: '4000 mtrs'}`

- insert multiple document using insertMany command
- find all documents from mountains
- find a single document using name

```js
var multiple = [
    {
        name: 'gaung ck', height: '6000 mtrs'
    },
    {
        name: 'triund', height: '8000 mtrs'
    }
]
use mountains
db.createCollection("himalayas")
db.himalayas.insert({name: 'Dhauldhar range', height: '4000 mtrs'})
db.himalayas.insertMany(multiple)
db.himalayas.find({name:"Dhauldhar range"})
db.himalayas.findOne({name:"Dhauldhar range"})
```

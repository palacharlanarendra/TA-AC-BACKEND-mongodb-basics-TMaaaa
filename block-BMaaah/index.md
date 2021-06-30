writeCode

Write code to execute below expressions.

1. Create a database named `blog`.
   use blog
2. Create a collection called 'articles'.
   db.createCollection('articles')
3. Insert multiple documents(at least 3) into articles. It should have fields
   db.article.insertMany([
   ... {
   ... title: 'hound of baskerville',
   ... details: 'thriller novel',
   ... author: {
   ... name: 'canon doyle',
   ... email: 'narendrapalacharla@gmail.com',
   ... age: 23,
   ... },
   ... tags: ['js', 'mongo'],
   ... },
   ... {
   ... title: 'hound of baskerville',
   ... details: 'thriller novel',
   ... author: {
   ... name: 'watson',
   ... email: 'palacharla@gmail.com',
   ... age: 23,
   ... },
   ... tags: ['HTML', 'CSS'],
   ... },
   ... ])

- title as string
- createdAt as date
- details as String
- author as nested object
  - author should have
    - name
    - email
    - age
    - example author: {name: 'abc', email: 'abc@gmail', age: 25}
- tags : Array of strings like ['html', 'css']

```js
// An article should look like in the database
{
  _id: 'some_random_id',
  title: '',
  details: '',
  author: {
    name: '',
    email: '',
    age: ''
  },
  tags: ['js', 'mongo']
}
```

4. Find all the articles using `db.COLLECTION_NAME.find()`
   db.article.find({})

5. Find a document using \_id field.
   db.article.findOne({"\_id" : ObjectId("60dc5b34d55625e975726d53")})

6. 1. Find documents using title
      db.article.find({title: 'hound of baskerville'})
7. 2. Find documents using author's name field.
8. Find document using a specific tag.
   db.article.find({"author.name": 'watson'})
9. Update title of a document using its \_id field.
   db.article.update({"\_id" : ObjectId("60dc5b34d55625e975726d53")},{$set:{"title":"samurai"}})

10. Update a author's name using article's title.
    db.article.update({"title":"samurai"},{$set:{"author.name":"narendra"}})
11. rename details field to description from all articles in articles collection.
    db.article.updateMany( {}, { $rename: { "details": "description" },{multi:true} } )
12. Add additional tag in a specific document.
    db.article.update( {title:"samurai"}, {$push:{tags:"nextjs"}})

13. Update an article's title using $set and without $set.
db.article.update({"title":"samurai"},{$set:{"author.name":"narendra"}})
    db.article.update({"title":"samurai"},{"author.name":"narendra"})

- Write the differences here ?
  with set it willupdate the existing key in object , wher a s with out set , the whole object will e replaced with this key and property.

13. find an article using title and increment it's auhtor's age by 5.
    db.article.update( {title:"hound of baskerville"},
    {$inc:{"author.age":5}} )
14. Delete a document using \_id field with `db.COLLECTION_NAME.remove()`.
    db.article.remove({"\_id" : ObjectId("60dc9989d55625e975726d56")})
    // Sample data

```js
db.users.insertMany([
  {
    age: 49,
    name: 'Maurice Brock',
    email: 'wuk@hibpiz.ch',
    gender: 'Female',
    sports: ['cricket', 'football'],
    scores: [24, 35, 18, 16],
    weight: 45,
  },
  {
    age: 37,
    birthday: '7/15/1986',
    name: 'Virgie Cunningham',
    email: 'ezogafa@de.gm',
    gender: 'Male',
    sports: ['football'],
    scores: [17, 35, 43],
    weight: 52,
  },
  {
    age: 48,
    birthday: '5/14/1961',
    name: 'Alexander Holt',
    email: 'han@mu.pe',
    gender: 'Male',
    sports: ['cricket', 'football', 'TT'],
    scores: [24, 30, 16],
    weight: 55,
  },
  {
    age: 53,
    birthday: '11/15/1963',
    name: 'Derek Dawson',
    email: 'polril@now.de',
    gender: 'Male',
    sports: ['cricket', 'hockey'],
    scores: [20, 15, 38, 23],
    weight: 49,
  },
  {
    age: 34,
    birthday: '7/24/1964',
    name: 'Cynthia Cobb',
    email: 'wujjarpob@jecimpar.gu',
    gender: 'Female',
    sports: ['cricket'],
    scores: [41, 17, 28],
    weight: 51,
  },
  {
    age: 33,
    birthday: '10/26/1982',
    name: 'Isabella Atkins',
    email: 'ononuzas@givhoz.ca',
    gender: 'Female',
    sports: ['cricket', 'football', 'hockey', 'TT'],
    scores: [14, 38, 29, 45, 20],
    weight: 49,
  },
  {
    age: 47,
    birthday: '10/12/1978',
    name: 'Katharine Bryan',
    email: 'zo@pebi.sa',
    gender: 'Male',
    sports: ['TT', 'hockey', 'khokho'],
    scores: [27, 20, 34],
    weight: 58,
  },
  {
    age: 41,
    birthday: '1/28/1991',
    name: 'Beatrice Fleming',
    email: 'ufufsa@pujizren.tk',
    gender: 'Female',
    sports: ['football', 'khokho'],
    scores: [30, 20, 15, 29, 43],
    weight: 47,
  },
  {
    age: 26,
    birthday: '3/23/1998',
    name: 'Tom Fields',
    email: 'wasodjow@ofaba.gf',
    gender: 'Female',
    sports: ['khokho'],
    scores: [37, 29, 18, 43, 49],
    weight: 50,
  },
  {
    age: 33,
    birthday: '11/14/1960',
    name: 'Steve Ortega',
    email: 'dupus@ca.ls',
    gender: 'Female',
    sports: ['cricket', 'football', 'hockey'],
    scores: [12, 15, 20],
    weight: 51,
  },
  {
    age: 24,
    birthday: '1/5/1994',
    name: 'Suraj Kumar',
    weight: 50,
    gender: 'Male',
    sports: ['football', 'cricket', 'TT'],
  },
]);
```

Insert above data into database to perform below queries:-

- Find all males who play cricket.
  db.users.find({gender:"Male",sports:'cricket'})

- Update user with extra golf field in sports array whose name is "Steve Ortega".
  db.users.update({name:"Steve Ortega"},{$push:{sports:"golf"}})
- Find all users who play either 'football' or 'cricket'.
  db.users.find({sports:{$in:['football','cricket']}})
- Find all users whose name includes 'ri' in their name.
  db.users.find({name:/ri/i})

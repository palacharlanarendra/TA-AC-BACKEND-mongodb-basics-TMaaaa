writeCode

Run these shell commands in mongo shell:

- db.version()
<!-- 4.4.6 -->
- db.stats()
<!-- 
{
	"db" : "india",
	"collections" : 0,
	"views" : 0,
	"objects" : 0,
	"avgObjSize" : 0,
	"dataSize" : 0,
	"storageSize" : 0,
	"totalSize" : 0,
	"indexes" : 0,
	"indexSize" : 0,
	"scaleFactor" : 1,
	"fileSize" : 0,
	"fsUsedSize" : 0,
	"fsTotalSize" : 0,
	"ok" : 1
} -->

- db.help()

Write code to

- create a database of your country name.
use india
- check list of databases to see newly created database.
show dbs
- check which database you are currently connected to ?
db
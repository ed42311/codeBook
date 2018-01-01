#
MongoDB Commands

this command well give you all the keys in a collection, I'm not sure where it stores the the output or for how long, but it seems useful
```
mr = db.runCommand({
"mapreduce" : "organization",
"map" : function() {
    for (var key in this) { emit(key, null); }
  },
"reduce" : function(key, stuff) { return null; },
"out": "organization" + "_keys"
});

db[mr.result].distinct("_id");
```

this will give you the number of collections in the database
```
db.getCollectionNames().length
```

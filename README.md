# LiteDB.Shell - compiled against `netcoreapp1.1`

I use this to browse [LiteDB](https://github.com/mbdavid/LiteDB) Database in Linux and Mac.
The code came directly from [LiteDB.Shell](https://github.com/mbdavid/LiteDB/tree/master/LiteDB.Shell) by [mbdavid](https://github.com/mbdavid)

All thanks goes to the original author of LiteDB project

# Usage
- Clone
- `dotnet restore & dotnet publish`
- `cd bin/Debug/netcoreapp1.1/publish/`
- `dotnet LiteDB.Shell.NetCore.dll <LiteDB File Location>`

```
Basic Shell Commands - try `help full` for all commands
=======================================================
> open <filename>|<connectionString>
    Open/Crete a new database

> show collections
    List all collections inside database

> db.<collection>.insert <jsonDoc>
    Insert a new document into collection

> db.<collection>.update <jsonDoc>
    Update a document inside collection

> db.<collection>.delete <filter>
    Delete documents using a filter clausule (see find)

> db.<collection>.find <filter> [skip N][limit N]
    Show filtered documents based on index search

> db.<collection>.count <filter>
    Show count rows according query filter

> db.<collection>.ensureIndex <field> [true|{options}]
    Create a new index document field. For unique key, use true

> db.<collection>.indexes
    List all indexes in this collection

<filter> = <field> [=|>|>=|<|<=|!=|like|between] <jsonValue>
    Filter query syntax

<filter> = (<filter> [and|or] <filter> [and|or] ...)
    Multi queries syntax

Try:
 > db.customers.insert { _id:1, name:"John Doe", age: 37 }
 > db.customers.ensureIndex name
 > db.customers.find name like "John"
 > db.customers.find name like "John" and _id between [0, 100] limit 10
```

> I could not find any GUI tool to browse LiteDB database in Unix platform, if you know one - please let me know.
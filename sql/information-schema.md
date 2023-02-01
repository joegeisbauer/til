# information_schema

From time to time, I just like to note things that I revisit often here rather than something I learned in particular that day. Today is one of those days, and this is one of those posts. Two of the most helpful views in a SQL database are `information_schema.tables` and `information_schema.columns` which give you information regarding the tables and columns in every table within the database. Although I rarely perform a query on these views as `select *` because I know more specifics about the information I need to query, the following will give you an overview of what information the tables contain while only returning 10 results:

`SELECT * FROM information_schema.tables WHERE table_schema=<db_name> LIMIT 10;`

and 

`SELECT * FROM information_schema.columns WHERE table_schema=<db_name> LIMIT 10;`
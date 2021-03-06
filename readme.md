Are you finding yourself writing long strings to build up a SQL query in python
to communicate with your SQL database? Then **sql_queries** is what you are looking for.
This package provides you with tools to build simple SQL queries from the ground up,
without having to manually type out formatted spaghetti strings over and over again. 
With this module, you'll no longer need codeblocks like this to write your queries :

```python
field = 'x'
table = 'a'
cond = 10

query = 'SELECT {} FROM {} WHERE {} = {}'.format(field, table, field, cond)
```

And this is only a simple example. 
The **sql_queries** equivalent of the above looks like this:

```python
from sql_query import sql_select

query = sql_select('x', 'a')
query.where(attr='x', cond=10)
```

A simple *SELECT-FROM-WHERE* example has been demonstrated above with the **sql_select** object.
This object also supports *GROUP BY*, *HAVING*, *ORDER BY*, *LIMIT* and *JOIN* statements.
There is also the **sql_update** object, which supports *UPDATE*, *SET* and *WHERE* statements.
Review the documentation to get a better understanding of how to implement these statements.
For a quick demo you can also view to one minute demo's to get you started with this module.
These can be found on [youtube](https://www.youtube.com/playlist?list=PLI4WFrsrAg8sCeBj5xdJ6n79_3Yq3Sz23).

Convert a **sql_query** (sub)object to a string using the build-in str() function to get your 
SQL query as text. The result can be used directly in for example pandas' *pd.read_sql_query()*
or sqlalchemy's *engine.execute(text())* methods.

### Known limitations for this version:
* Exceptions haven't yet been properly implemented.
* The .join method can only be used in combination with loading plain field (e.g. using COUNT(FieldX) in the SELECT statement will result in an invalid query)
* The module has only been properly tested with a SQLite3 database.

### Tutorial video's
A series of one minute demo's to get started with this module can be found on [youtube](https://www.youtube.com/playlist?list=PLI4WFrsrAg8sCeBj5xdJ6n79_3Yq3Sz23).

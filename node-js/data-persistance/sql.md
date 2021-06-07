# SQL

![](../../.gitbook/assets/kisspng-microsoft-sql-server-mysql-database-logo-5b098c6ee92a46.0488681015273524309551.png)

These databases are called relational because we can do relations between the tables to share data or referring to certain fields of another table in the table, they have their own syntax that you need to execute in order to retrieve data, update this data or even delete it.

These tables are organised in the same way a spreadsheet is done, they're composed of rows, columns and cells.

![How a common SQL database looks like](../../.gitbook/assets/image%20%2830%29.png)

In the image above, we can see how a common database is distributed, we can see that the main table of information is the Movies table, and then every table is relational with another table that expands his data, for example the column MovieID is joined with the MovieGenres table and this table is relational with Genres table, this make that inside the MovieID column we have all this data available.

If we want to get all the data for a single entry we can do something like this:

```sql
SELECT * FROM Movies WHERE Title='Titanic';
```

This query \(that's how it's called the commands that we send to the database\) we're getting all the movies that his name is exactly Titanic.

We can also update this row.

```sql
UPDATE Movies SET ReleaseYear=1997 WHERE Title='Titanic';
```

And when we don't longer want this row remove, we can even remove all the rows that match our criteria.

```sql
DELETE FROM Movies WHERE GenreID = 'Action';
```

And finally insert new data via the query. We need to specify every column and then into the values what this column will contain.

```sql
INSERT INTO Movies (MovieID, DirectorID, GenreId, Title, ReleaseYear, Rating, Plot, MovieLength)
VALUES (54, 32, 12, 'Interstellar', 2014, 10, 'Story Circle Method', 169);
```

The most famous SQL Databases are: Postgres, MySQL, Microsoft SQL or Oracle. 


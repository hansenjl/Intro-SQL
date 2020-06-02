# Intro to SQL

## SQL stands for Structured Query Language

### Structured Query Language and is a language that allows us to:
- Store / persist information
- Manipulate that information

### SQLite3 is a relational database.
A relational database is a type of database that stores and provides access to data points that are related to one another

Some specific actions that we can do are CRUD actions, a common acronym we’ll see throughout the program, web development, and computing in general:
- Create data
- Read data
- Update data
- Delete data

1. Write the SQL to return all of the rows in the artists table?

```SQL
SELECT * FROM artists;
```

2. Write the SQL to select the artist with the name "Black Sabbath"
```SQL
SELECT * FROM artists WHERE name = 'Black Sabbath'
```
Play with:
```SQL
SELECT * FROM artists WHERE name LIKE 'Black%'
Where % sign is filled in by SQL for anything.
```

3. Write the SQL to create a table named 'fans' with an auto incrementing ID that's a primary key and a name field of type text

```sql
CREATE TABLE fans (id INTEGER PRIMARY KEY, name TEXT);
```

4. Write the SQL to alter the fans table to have a artist_id column type integer?

```sql
ALTER TABLE fans ADD COLUMN  artist_id INTEGER;
```

5. Write the SQL to add yourself as a fan of the Black Eyed Peas? ArtistId **169**

```sql
INSERT INTO fans (name, artist_id) VALUES ("Alex", 169);
```

6. Check out the [Faker gem](https://github.com/stympy/faker). `gem install faker`, open up irb, run `require 'faker'` and then generate a fake name for yourself using `Faker::Name.name`. How would you update your name in the fans table to be your new name?

   ```sql
UPDATE fans
SET name = 'Bob'
WHERE name= 'Alex';
   ```

7. Write the SQL to return fans that are not fans of the black eyed peas.

```sql
SELECT * FROM fans WHERE artist_id != 169;
```

8. Write the SQL to display an artists name next to their album title

```sql
SELECT artists.name, albums.title FROM ARTISTS
JOIN albums
ON albums.ArtistId = artists.ArtistId;
```

<!-- # mash_server






-- List all tables
\dt

-- Describe a specific table
\d your_table_name

-- Show current database
SELECT current_database();

-- Run a simple query
SELECT * FROM your_table_name;

-- List all databases
\l

-- List all schemas
\dn

-- List all users/roles
\du

-- Check connection info
\conninfo

-- Exit psql
\q











1. Connect to the mashdb Database
First, switch to the mashdb database by reconnecting:

bash
 
\c mashdb
This will change your current database connection to mashdb.

2. List Tables in mashdb
After connecting to mashdb, list all the tables:

sql
 
\dt
3. Describe a Table
If there are tables present, you can describe one using:

sql
 
\d table_name
Replace table_name with the actual table name.

Summary of Commands
bash
 
-- Connect to mashdb
\c mashdb

-- List all tables in mashdb
\dt

-- Describe a specific table
\d table_name


If mashdb also does not contain any tables, you might need to create them or ensure you're in the correct database











$env:PGPASSWORD = "1csUoYvGJUbUwmRO0G15ASpUPnux4JEK"
psql -h dpg-cqkfgrrqf0us73c9ersg-a.oregon-postgres.render.com -U mash_db_user -d mash_db

1. Create a New Artist
POST Request URL: http://localhost:3000/artists

JSON Body:

json
Copy code
{
  "name": "John Doe",
  "username": "john_doe_music",
  "description": "An independent artist with a unique sound.",
  "profilePicture": "https://example.com/images/john_doe.png",
  "walletAddress": "0x1234567890abcdef",
  "instagram": "https://instagram.com/john_doe_music",
  "tiktok": "https://tiktok.com/@john_doe_music",
  "twitter": "https://twitter.com/john_doe_music",
  "website": "https://johndoemusic.com"
}
2. Add Featured Content for an Artist
POST Request URL: http://localhost:3000/artists/1/featured-content

JSON Body:

json
Copy code
{
  "image": "https://example.com/images/featured_content_1.png",
  "name": "Hit Single - Summer Vibes"
}
3. Add New Releases for an Artist
POST Request URL: http://localhost:3000/artists/1/new-releases

JSON Body:

json
Copy code
{
  "image": "https://example.com/images/new_release_1.png",
  "name": "Album - Chill Beats Vol. 1"
}
4. Update an Existing Artist
PUT Request URL: http://localhost:3000/artists/1

JSON Body:

json
Copy code
{
  "name": "John Doe Updated",
  "username": "john_doe_music_updated",
  "description": "An updated description for the artist.",
  "profilePicture": "https://example.com/images/john_doe_updated.png",
  "walletAddress": "0xabcdef1234567890",
  "instagram": "https://instagram.com/john_doe_music_updated",
  "tiktok": "https://tiktok.com/@john_doe_music_updated",
  "twitter": "https://twitter.com/john_doe_music_updated",
  "website": "https://johndoemusicupdated.com"
}
5. Get All Artists
GET Request URL: http://localhost:3000/artists

No JSON body required.

6. Get All Featured Content for an Artist
GET Request URL: http://localhost:3000/artists/1/featured-content

No JSON body required.

7. Get All New Releases for an Artist
GET Request URL: http://localhost:3000/artists/1/new-releases

No JSON body required.

8. Delete an Artist by ID
DELETE Request URL: http://localhost:3000/artists/1

No JSON body required.

9. Delete Featured Content by ID
DELETE Request URL: http://localhost:3000/artists/1/featured-content/1

No JSON body required.

10. Delete New Release by ID
DELETE Request URL: http://localhost:3000/artists/1/new-releases/1

No JSON body required.

Replace the :id in the URLs with the actual artist ID, featured content ID, or new release ID as needed. These JSON payloads should work well for testing the corresponding endpoints in your Node.js Express application using Postman.


 -->

Here's the content formatted for a `README.md` file:

---

# Mash Server

## Database Management with `psql`

### Basic Commands

```bash
-- List all tables
\dt

-- Describe a specific table
\d your_table_name

-- Show current database
SELECT current_database();

-- Run a simple query
SELECT * FROM your_table_name;

-- List all databases
\l

-- List all schemas
\dn

-- List all users/roles
\du

-- Check connection info
\conninfo

-- Exit psql
\q
```

### Connecting to the `mashdb` Database

1. **Connect to `mashdb`:**

    ```bash
    \c mashdb
    ```

    This will change your current database connection to `mashdb`.

2. **List Tables in `mashdb`:**

    ```bash
    \dt
    ```

3. **Describe a Table:**

    ```bash
    \d table_name
    ```

    Replace `table_name` with the actual table name.

### Summary of Commands

```bash
-- Connect to mashdb
\c mashdb

-- List all tables in mashdb
\dt

-- Describe a specific table
\d table_name
```

### Connecting to the Remote Database

```bash
$env:PGPASSWORD = "MashLabs1!"
psql -h database-mash1.c6r2kb9hs7mn.us-east-1.rds.amazonaws.com -U postgres database-mash1

``` 
## API Endpoints

### 1. Create a New Artist

- **POST Request URL:** `http://localhost:3000/artists`
- **JSON Body:**

    ```json
    {
  "name": "Mike Bellamy1",
  "description": "Mike Bellamy is a rising star in the indie rock scene, known for his electrifying performances and emotive songwriting. With a passion for crafting compelling melodies and thought-provoking lyrics, Mike has been making waves since his debut in 2020.",
  "profilePicture": "https://firebasestorage.googleapis.com/v0/b/mash-8645e.appspot.com/o/profile.jpg?alt=media&token=0c495349-1ef0-4c80-9bfa-cc2ec1c5e4c9",
  "walletAddress": "0xabcdef1234567890"
    }
    ```

### 2. Add Featured Content for an Artist

- **POST Request URL:** `http://localhost:3000/artists/1/featured-content`
- **JSON Body:**

    ```json
        {
          "type": "Painting",
          "creator": "Mike Bellamy",
          "file_name": "Tragically Royal",
          "file": "https://firebasestorage.googleapis.com/v0/b/mash-8645e.appspot.com/o/3.Tragically%20Royal.jpeg?alt=media&token=36a5be26-cc70-4f1d-9d8c-459a7d1cd791",
          "price": 0.02,
          "scarcity": "199 / 5,000",
          "utility": "10% off tattoo",
          "tags": ["skull", "dark", "medieval"],
          "geo": "NYC"
        }
    ```

### 3. Add New Releases for an Artist

- **POST Request URL:** `http://localhost:3000/artists/1/new-releases`
- **JSON Body:**

    ```json
      {
      "type": "Song",
      "creator": "THISMINORITY",
      "file_name": "Jungle",
      "song_url": "https://open.spotify.com/track/3L181zUSmJBhClIwqKj911?si=d0c958c1c6b849fa",
      "price": ".04 ETH (~$107)",
      "scarcity": "100",
      "utility": "20% off live shows",
      "tags": ["HipHop", "indierap", "workout", "city"],
      "geo": "NYC",
      "image_url": "https://example.com/path/to/image.jpg"
        }

    ```

### 4. Update an Existing Artist

- **PUT Request URL:** `http://localhost:3000/artists/1`
- **JSON Body:**

    ```json
    {
      "name": "John Doe Updated",
      "username": "john_doe_music_updated",
      "description": "An updated description for the artist.",
      "profilePicture": "https://example.com/images/john_doe_updated.png",
      "walletAddress": "0xabcdef1234567890" 
    }
    ```

### 5. Get All Artists

- **GET Request URL:** `http://localhost:3000/artists`
- **No JSON body required.**

### 6. Get All Featured Content for an Artist

- **GET Request URL:** `http://localhost:3000/artists/1/featured-content`
- **No JSON body required.**

### 7. Get All New Releases for an Artist

- **GET Request URL:** `http://localhost:3000/artists/1/new-releases`
- **No JSON body required.**

### 8. Delete an Artist by ID

- **DELETE Request URL:** `http://localhost:3000/artists/1`
- **No JSON body required.**

### 9. Delete Featured Content by ID

- **DELETE Request URL:** `http://localhost:3000/artists/1/featured-content/1`
- **No JSON body required.**

### 10. Delete New Release by ID

- **DELETE Request URL:** `http://localhost:3000/artists/1/new-releases/1`
- **No JSON body required.**

> **Note:** Replace the `:id` in the URLs with the actual artist ID, featured content ID, or new release ID as needed. These JSON payloads should work well for testing the corresponding endpoints in your Node.js Express application using Postman.

---













### 1. **SQL to Create the New Table**

You'll need to execute the following SQL statements to drop the existing table and create a new one with `id` as the primary key:

```sql
-- Drop the existing table if it exists
DROP TABLE IF EXISTS featured_content;

-- Create the new table with 'id' as the primary key
CREATE TABLE featured_content (
    id SERIAL PRIMARY KEY,
    type VARCHAR(100) NOT NULL,
    creator VARCHAR(100) NOT NULL,
    file_name VARCHAR(255) NOT NULL,
    file TEXT NOT NULL,
    price NUMERIC(10, 2) NOT NULL,
    scarcity VARCHAR(100) NOT NULL,
    utility TEXT,
    tags TEXT[],
    geo VARCHAR(255),
    createdat TIMESTAMP WITHOUT TIME ZONE DEFAULT CURRENT_TIMESTAMP,
    artistid BIGINT REFERENCES artists(id) ON DELETE CASCADE
);
```

### 2. **POST Endpoint**

Here’s how the `POST` endpoint would look to insert data into the updated `featured_content` table:

```javascript
app.post('/artists/:artistId/featured-content', async (req, res) => {
  const { artistId } = req.params;
  const { type, creator, file_name, file, price, scarcity, utility, tags, geo } = req.body;

  try {
    const result = await pool.query(
      `INSERT INTO featured_content (type, creator, file_name, file, price, scarcity, utility, tags, geo, createdat, artistid) 
       VALUES ($1, $2, $3, $4, $5, $6, $7, $8, $9, NOW(), $10) 
       RETURNING *`,
      [type, creator, file_name, file, price, scarcity, utility, tags, geo, artistId]
    );
    
    res.status(201).json(result.rows[0]);
  } catch (err) {
    res.status(500).json({ error: err.message });
  }
});
```

### 3. **Example JSON Request Body**

Here’s a JSON example for inserting data into the new table:

```json
{
  "type": "Drawing",
  "creator": "Mike Bellamy",
  "file_name": "Last Knight",
  "file": "https://firebasestorage.googleapis.com/v0/b/mash-8645e.appspot.com/o/1.Last%20Knight.jpeg?alt=media&token=406c59bd-15fc-4a73-9b20-60b04a9e85cf",
  "price": 0.02,
  "scarcity": "240 / 5,000",
  "utility": "10% off tattoo",
  "tags": ["skull", "medieval", "spooky", "lonely"],
  "geo": "NYC"
}
```

### Summary

- **SQL Commands**: The provided SQL commands drop the existing table and create a new table with `id` as the primary key.
- **POST Endpoint**: Adjusted to fit the new schema.
- **JSON Request Body**: Updated to match the new schema without the `order` field.

This setup will allow you to insert new entries into your `featured_content` table, and each entry will have a unique `id` automatically assigned.
 























Certainly! Here's how you can adjust the table schema to use `id` instead of `order`, and update your `POST` endpoint and JSON request accordingly.

### 1. **SQL to Create the New Table**

You'll need to execute the following SQL statements to drop the existing table and create a new one with `id` as the primary key:

```sql
-- Drop the existing table if it exists
DROP TABLE IF EXISTS featured_content;

-- Create the new table with 'id' as the primary key
CREATE TABLE featured_content (
    id SERIAL PRIMARY KEY,
    type VARCHAR(100) NOT NULL,
    creator VARCHAR(100) NOT NULL,
    file_name VARCHAR(255) NOT NULL,
    file TEXT NOT NULL,
    price NUMERIC(10, 2) NOT NULL,
    scarcity VARCHAR(100) NOT NULL,
    utility TEXT,
    tags TEXT[],
    geo VARCHAR(255),
    createdat TIMESTAMP WITHOUT TIME ZONE DEFAULT CURRENT_TIMESTAMP,
    artistid BIGINT REFERENCES artists(id) ON DELETE CASCADE
);
```

### 2. **POST Endpoint**

Here’s how the `POST` endpoint would look to insert data into the updated `featured_content` table:

```javascript
app.post('/artists/:artistId/featured-content', async (req, res) => {
  const { artistId } = req.params;
  const { type, creator, file_name, file, price, scarcity, utility, tags, geo } = req.body;

  try {
    const result = await pool.query(
      `INSERT INTO featured_content (type, creator, file_name, file, price, scarcity, utility, tags, geo, createdat, artistid) 
       VALUES ($1, $2, $3, $4, $5, $6, $7, $8, $9, NOW(), $10) 
       RETURNING *`,
      [type, creator, file_name, file, price, scarcity, utility, tags, geo, artistId]
    );
    
    res.status(201).json(result.rows[0]);
  } catch (err) {
    res.status(500).json({ error: err.message });
  }
});
```

### 3. **Example JSON Request Body**

Here’s a JSON example for inserting data into the new table:

```json
{
  "type": "Drawing",
  "creator": "Mike Bellamy",
  "file_name": "Last Knight",
  "file": "https://firebasestorage.googleapis.com/v0/b/mash-8645e.appspot.com/o/1.Last%20Knight.jpeg?alt=media&token=406c59bd-15fc-4a73-9b20-60b04a9e85cf",
  "price": 0.02,
  "scarcity": "240 / 5,000",
  "utility": "10% off tattoo",
  "tags": ["skull", "medieval", "spooky", "lonely"],
  "geo": "NYC"
}
```

### Summary

- **SQL Commands**: The provided SQL commands drop the existing table and create a new table with `id` as the primary key.
- **POST Endpoint**: Adjusted to fit the new schema.
- **JSON Request Body**: Updated to match the new schema without the `order` field.

This setup will allow you to insert new entries into your `featured_content` table, and each entry will have a unique `id` automatically assigned.


```json
{
  "type": "Drawing",
  "creator": "Mike Bellamy",
  "file_name": "Golden Buddah",
  "file": "https://firebasestorage.googleapis.com/v0/b/mash-8645e.appspot.com/o/2.Golden%20Buddah.jpeg?alt=media&token=8c1520ce-f62e-4658-91c2-49a7b74430d2",
  "price": 0.02,
  "scarcity": "144 / 5,000",
  "utility": "10% off tattoo",
  "tags": ["baby", "Buddah", "peaceful", "spiritual"],
  "geo": "NYC"
}
```

 ```json
{
  "type": "Painting",
  "creator": "Mike Bellamy",
  "file_name": "Tragically Royal",
  "file": "https://firebasestorage.googleapis.com/v0/b/mash-8645e.appspot.com/o/3.Tragically%20Royal.jpeg?alt=media&token=36a5be26-cc70-4f1d-9d8c-459a7d1cd791",
  "price": 0.02,
  "scarcity": "199 / 5,000",
  "utility": "10% off tattoo",
  "tags": ["skull", "dark", "medieval"],
  "geo": "NYC"
}
```

 ```json
{
  "type": "Photography",
  "creator": "Mike Bellamy",
  "file_name": "Shaman",
  "file": "https://firebasestorage.googleapis.com/v0/b/mash-8645e.appspot.com/o/4.Shaman.jpeg?alt=media&token=c583457b-e593-4260-9418-39679542cf07",
  "price": 0.02,
  "scarcity": "527 / 5,000",
  "utility": "10% off tattoo",
  "tags": ["baby", "magic", "woods", "mysterious"],
  "geo": "NYC"
}
```

 ```json
{
  "type": "Painting",
  "creator": "Mike Bellamy",
  "file_name": "Behind The Mask",
  "file": "https://firebasestorage.googleapis.com/v0/b/mash-8645e.appspot.com/o/5.Behind%20The%20Mask.jpeg?alt=media&token=02748691-1c38-4377-a3bb-7befc4effb4b",
  "price": 0.02,
  "scarcity": "741 / 5,000",
  "utility": "10% off tattoo",
  "tags": ["skull", "stilllife"],
  "geo": "NYC"
}
```

 1. **Valhalla**
```json
{
  "type": "Painting",
  "creator": "Mike Bellamy",
  "file_name": "Valhalla",
  "file": "https://firebasestorage.googleapis.com/v0/b/mash-8645e.appspot.com/o/6.Valhalla.jpeg?alt=media&token=a2b204fc-9a60-4e6b-9d29-b20fb90fc01f",
  "price": 0.02,
  "scarcity": "624 / 5,000",
  "utility": "10% off tattoo",
  "tags": ["skull", "viking", "strong"],
  "geo": "NYC"
}
```

2. **Pray For LA**
```json
{
  "type": "Drawing",
  "creator": "Mike Bellamy",
  "file_name": "Pray For LA",
  "file": "https://firebasestorage.googleapis.com/v0/b/mash-8645e.appspot.com/o/7.Pray%20For%20LA.jpeg?alt=media&token=b5ed86fb-cc65-47fd-9bae-2a9ddb70ab6a",
  "price": 0.02,
  "scarcity": "404 / 5,000",
  "utility": "10% off tattoo",
  "tags": ["LA", "hands", "neon", "urban"],
  "geo": "NYC"
}
```

3. **Behind The Veil**
```json
{
  "type": "Photography",
  "creator": "Mike Bellamy",
  "file_name": "Behind The Veil",
  "file": "https://firebasestorage.googleapis.com/v0/b/mash-8645e.appspot.com/o/8.Behind%20The%20Veil.jpeg?alt=media&token=fcf36cb7-6d4c-4939-8b57-457d8adadacd",
  "price": 0.02,
  "scarcity": "801 / 5,000",
  "utility": "10% off tattoo",
  "tags": ["spooky", "horror", "angry"],
  "geo": "NYC"
}
```

4. **Frozen In Time**
```json
{
  "type": "Painting",
  "creator": "Mike Bellamy",
  "file_name": "Frozen In Time",
  "file": "https://firebasestorage.googleapis.com/v0/b/mash-8645e.appspot.com/o/9.Frozen%20In%20Time.jpeg?alt=media&token=821f202c-2806-40b5-bbf5-3972dfd0fb77",
  "price": 0.02,
  "scarcity": "781 / 5,000",
  "utility": "10% off tattoo",
  "tags": ["animals", "bird", "skeleton"],
  "geo": "NYC"
}
```

5. **Faced**
```json
{
  "type": "Photography",
  "creator": "Mike Bellamy",
  "file_name": "Faced",
  "file": "https://firebasestorage.googleapis.com/v0/b/mash-8645e.appspot.com/o/10.Faced.jpeg?alt=media&token=73cc49cc-5deb-4d97-8d0f-4476975791e5",
  "price": 0.02,
  "scarcity": "681 / 5,000",
  "utility": "10% off tattoo",
  "tags": ["woman", "skeleton", "dancing", "spooky"],
  "geo": "NYC"
}
```

6. **Dapper Don’t Matter**
```json
{
  "type": "Drawing",
  "creator": "Mike Bellamy",
  "file_name": "Dapper Don’t Matter",
  "file": "https://firebasestorage.googleapis.com/v0/b/mash-8645e.appspot.com/o/11.Dapper%20Don%E2%80%99t%20Matter.jpeg?alt=media&token=7106a2a7-a1df-40a1-99d4-06bce7547fe8",
  "price": 0.02,
  "scarcity": "372 / 5,000",
  "utility": "10% off tattoo",
  "tags": ["skeleton", "dapper", "fun"],
  "geo": "NYC"
}
```

7. **Dragonsuit**
```json
{
  "type": "Drawing",
  "creator": "Mike Bellamy",
  "file_name": "Dragonsuit",
  "file": "https://firebasestorage.googleapis.com/v0/b/mash-8645e.appspot.com/o/12.Dragonsuit.jpeg?alt=media&token=5a9d51c3-3774-4683-a459-418b4a5b4f8f",
  "price": 0.02,
  "scarcity": "521 / 5,000",
  "utility": "10% off tattoo",
  "tags": ["dragon", "tattoo", "energetic"],
  "geo": "NYC"
}
```

8. **Voyager**
```json
{
  "type": "Photography",
  "creator": "Mike Bellamy",
  "file_name": "Voyager",
  "file": "https://firebasestorage.googleapis.com/v0/b/mash-8645e.appspot.com/o/13.Voyager.jpeg?alt=media&token=e473a191-a3e3-4a0f-b8ad-ab92eea67104",
  "price": 0.02,
  "scarcity": "894 / 5,000",
  "utility": "10% off tattoo",
  "tags": ["baby", "space", "ambient"],
  "geo": "NYC"
}
```

9. **Roosternoose**
```json
{
  "type": "Drawing",
  "creator": "Mike Bellamy",
  "file_name": "Roosternoose",
  "file": "https://firebasestorage.googleapis.com/v0/b/mash-8645e.appspot.com/o/14.Roosternoose.jpeg?alt=media&token=9c6a6c60-8637-4531-8e36-28397d333687",
  "price": 0.02,
  "scarcity": "174 / 5,000",
  "utility": "10% off tattoo",
  "tags": ["animals", "rooster", "country"],
  "geo": "NYC"
}
```

10. **Samurai Skull**
```json
{
  "type": "Drawing",
  "creator": "Mike Bellamy",
  "file_name": "Samurai Skull",
  "file": "https://firebasestorage.googleapis.com/v0/b/mash-8645e.appspot.com/o/15.Samurai%20Skull.jpeg?alt=media&token=0bc034a5-a346-433d-944b-4f1f2575e520",
  "price": 0.02,
  "scarcity": "104 / 5,000",
  "utility": "10% off tattoo",
  "tags": ["skull", "martial arts", "mad", "aggressive"],
  "geo": "NYC"
}
```

















To modify the `new_releases` table according to the new fields provided, you'll need to drop the existing table and create a new one with the specified fields. Here's how you can do this:

### 1. Drop the Existing Table
First, drop the existing `new_releases` table:

```sql
DROP TABLE IF EXISTS new_releases;
```

### 2. Create the New Table
Next, create the new `new_releases` table with the specified fields:

```sql
CREATE TABLE new_releases (
    id SERIAL PRIMARY KEY,
    type VARCHAR(50) NOT NULL,
    creator VARCHAR(100) NOT NULL,
    file_name VARCHAR(100) NOT NULL,
    song_url TEXT NOT NULL,
    price VARCHAR(50) NOT NULL,
    scarcity VARCHAR(50) NOT NULL,
    utility TEXT NOT NULL,
    tags TEXT[] NOT NULL,
    geo VARCHAR(100) NOT NULL,
    image_url TEXT NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    artistId BIGINT REFERENCES artists(id) ON DELETE CASCADE
);
```

### 3. Example Insert Statements
Here are some example `INSERT` statements to add data into the newly created table:

```sql
INSERT INTO new_releases (type, creator, file_name, song_url, price, scarcity, utility, tags, geo, image_url)
VALUES 
('Song', 'THISMINORITY', 'Jungle', 'https://open.spotify.com/track/3L181zUSmJBhClIwqKj911?si=d0c958c1c6b849fa', '.04 ETH (~$107)', '100', '20% off live shows', ARRAY['HipHop', 'indierap', 'workout', 'city'], 'NYC', 'https://firebasestorage.googleapis.com/v0/b/mash-8645e.appspot.com/o/6.Valhalla.jpeg?alt=media&token=a2b204fc-9a60-4e6b-9d29-b20fb90fc01f');
```

### 4. JSON Example for Insertion

Here’s an example of how the data might look in JSON format before being inserted into the table:

```json
{
  "type": "Song",
  "creator": "THISMINORITY",
  "file_name": "Jungle",
  "song_url": "https://open.spotify.com/track/3L181zUSmJBhClIwqKj911?si=d0c958c1c6b849fa",
  "price": ".04 ETH (~$107)",
  "scarcity": "100",
  "utility": "20% off live shows",
  "tags": ["HipHop", "indierap", "workout", "city"],
  "geo": "NYC",
  "image_url": "https://firebasestorage.googleapis.com/v0/b/mash-8645e.appspot.com/o/6.Valhalla.jpeg?alt=media&token=a2b204fc-9a60-4e6b-9d29-b20fb90fc01f"
}
```



 
1. **Gallery**

```json
{
  "type": "Song",
  "creator": "THISMINORITY",
  "file_name": "Gallery",
  "song_url": "https://open.spotify.com/track/5737VL5CXm8S7z1ffuUGXr?si=5dc615e9ad664f8d",
  "price": ".04 ETH (~$107)",
  "scarcity": "/ 100",
  "utility": "20% off live shows",
  "tags": ["HipHop", "chill", "city", "hybrid"],
  "geo": "NYC",
  "image_url": "https://firebasestorage.googleapis.com/v0/b/mash-8645e.appspot.com/o/Mike%20Bellamy%20Music%2F2.Gallery.jpg?alt=media&token=50fae69c-fcf9-4708-9b77-7e833ba5ab3e"
}
```

2. **BELLS**

```json
{
  "type": "Song",
  "creator": "THISMINORITY",
  "file_name": "BELLS",
  "song_url": "https://open.spotify.com/track/0JfqEhTaOQZtkL43cH4uLA?si=3155650bbfe64297",
  "price": ".04 ETH (~$107)",
  "scarcity": "/ 100",
  "utility": "20% off live shows",
  "tags": ["HipHop", "hybrid", "driving"],
  "geo": "NYC",
  "image_url": "https://firebasestorage.googleapis.com/v0/b/mash-8645e.appspot.com/o/Mike%20Bellamy%20Music%2F3.BELLS.jpg?alt=media&token=29d2e5e2-ec93-4d61-924b-0a83d31c2a92"
}
```

3. **What Is You Servin**

```json
{
  "type": "Song",
  "creator": "THISMINORITY",
  "file_name": "What Is You Servin",
  "song_url": "https://open.spotify.com/track/4ncUY4wtyvNez3VhSLMp0P?si=3bc96caa738c4dba",
  "price": ".04 ETH (~$107)",
  "scarcity": "/ 100",
  "utility": "20% off live shows",
  "tags": ["HipHop", "hybrid", "edm", "dance"],
  "geo": "NYC",
  "image_url": "https://firebasestorage.googleapis.com/v0/b/mash-8645e.appspot.com/o/Mike%20Bellamy%20Music%2F4.What%20Is%20You%20Servin.jpg?alt=media&token=f8756454-5ffa-44b7-a9b4-94fe7169f6ad"
}
```

4. **Let Me Have This**

```json
{
  "type": "Song",
  "creator": "THISMINORITY",
  "file_name": "Let Me Have This",
  "song_url": "https://open.spotify.com/track/46yqqMLEwmbTpqMrtv74fZ?si=c3f0ea93ee5348a0",
  "price": ".04 ETH (~$107)",
  "scarcity": "/ 100",
  "utility": "20% off live shows",
  "tags": ["HipHop", "summertime", "chillin"],
  "geo": "NYC",
  "image_url": "https://firebasestorage.googleapis.com/v0/b/mash-8645e.appspot.com/o/Mike%20Bellamy%20Music%2F5.Let%20Me%20Have%20This.jpg?alt=media&token=aac2d044-02e0-4bc7-9977-13b10c398954"
}
```

5. **Dangerous Satisfaction**

```json
{
  "type": "Song",
  "creator": "THISMINORITY",
  "file_name": "Dangerous Satisfaction",
  "song_url": "https://open.spotify.com/track/5lmV6cXLFw8D1DGoJ3S12v?si=14e08841b22542cd",
  "price": ".04 ETH (~$107)",
  "scarcity": "/ 100",
  "utility": "20% off live shows",
  "tags": ["HipHop"],
  "geo": "NYC",
  "image_url": "https://firebasestorage.googleapis.com/v0/b/mash-8645e.appspot.com/o/Mike%20Bellamy%20Music%2F6.Dangerous%20Satisfaction.jpg?alt=media&token=072f2623-4e42-4737-b93c-27d640488f65"
}
```

6. **Sun Down**

```json
{
  "type": "Song",
  "creator": "THISMINORITY",
  "file_name": "Sun Down",
  "song_url": "https://open.spotify.com/track/5cS1LUmGfxwh5OU4KrJz5u?si=ee744e9b7fc94aff",
  "price": ".04 ETH (~$107)",
  "scarcity": "/ 100",
  "utility": "20% off live shows",
  "tags": ["HipHop"],
  "geo": "NYC",
  "image_url": "https://firebasestorage.googleapis.com/v0/b/mash-8645e.appspot.com/o/Mike%20Bellamy%20Music%2F7.Sun%20Down.jpg?alt=media&token=02523ade-3100-47f2-ad6f-e6daf5cf21bb"
}
```

7. **BTWD**

```json
{
  "type": "Song",
  "creator": "THISMINORITY",
  "file_name": "BTWD",
  "song_url": "https://open.spotify.com/track/5f3fjm5HGNRLNtLnCM1I3h?si=1933ec7d27f3411e",
  "price": ".04 ETH (~$107)",
  "scarcity": "/ 100",
  "utility": "20% off live shows",
  "tags": ["HipHop"],
  "geo": "NYC",
  "image_url": "https://firebasestorage.googleapis.com/v0/b/mash-8645e.appspot.com/o/Mike%20Bellamy%20Music%2F8.BTWD.jpg?alt=media&token=80f29978-a7f4-48d4-a6ce-a8e9807383e2"
}
```

8. **CHK**

```json
{
  "type": "Song",
  "creator": "THISMINORITY",
  "file_name": "CHK",
  "song_url": "https://open.spotify.com/track/5d9lm7UkSbUyzIElZmgs05?si=be82e691ff0041ee",
  "price": ".04 ETH (~$107)",
  "scarcity": "/ 100",
  "utility": "20% off live shows",
  "tags": ["HipHop"],
  "geo": "NYC",
  "image_url": "https://firebasestorage.googleapis.com/v0/b/mash-8645e.appspot.com/o/Mike%20Bellamy%20Music%2F9.CHK.jpg?alt=media&token=da84efe1-a5cf-476c-a774-66c102d50852"
}
```

9. **STING**

```json
{
  "type": "Song",
  "creator": "THISMINORITY",
  "file_name": "STING",
  "song_url": "https://open.spotify.com/track/1dZmoar16F6Cz2ikeB42Lc?si=196fd74633454334",
  "price": ".04 ETH (~$107)",
  "scarcity": "/ 100",
  "utility": "20% off live shows",
  "tags": ["HipHop"],
  "geo": "NYC",
  "image_url": "https://firebasestorage.googleapis.com/v0/b/mash-8645e.appspot.com/o/Mike%20Bellamy%20Music%2F9.CHK.jpg?alt=media&token=da84efe1-a5cf-476c-a774-66c102d50852"
}
```

10. **NCPS**

```json
{
  "type": "Song",
  "creator": "THISMINORITY",
  "file_name": "NCPS",
  "song_url": "https://open.spotify.com/track/1dZmoar16F6Cz2ikeB42Lc?si=196fd74633454334",
  "price": ".04 ETH (~$107)",
  "scarcity": "/ 100",
  "utility": "20% off live shows",
  "tags": ["HipHop"],
  "geo": "NYC",
  "image_url": "https://firebasestorage.googleapis.com/v0/b/mash-8645e.appspot.com/o/Mike%20Bellamy%20Music%2F9.CHK.jpg?alt=media&

token=da84efe1-a5cf-476c-a774-66c102d50852"
}
```

 1. **EBT**

```json
{
  "type": "Song",
  "creator": "THISMINORITY",
  "file_name": "EBT",
  "song_url": "https://open.spotify.com/track/2m5bSdpZO8H09NQI5Ot9r0?si=5fe654b2dfb54bfe",
  "price": ".04 ETH (~$107)",
  "scarcity": "/ 100",
  "utility": "20% off live shows",
  "tags": ["HipHop"],
  "geo": "NYC",
  "image_url": "https://firebasestorage.googleapis.com/v0/b/mash-8645e.appspot.com/o/Mike%20Bellamy%20Music%2F9.CHK.jpg?alt=media&token=da84efe1-a5cf-476c-a774-66c102d50852"
}
```

2. **MEDI**

```json
{
  "type": "Song",
  "creator": "THISMINORITY",
  "file_name": "MEDI",
  "song_url": "https://open.spotify.com/track/7oOeci7j3KNSuAD3IUPSYz?si=431db1ed617d498b",
  "price": ".04 ETH (~$107)",
  "scarcity": "/ 100",
  "utility": "20% off live shows",
  "tags": ["HipHop"],
  "geo": "NYC",
  "image_url": "https://firebasestorage.googleapis.com/v0/b/mash-8645e.appspot.com/o/Mike%20Bellamy%20Music%2F9.CHK.jpg?alt=media&token=da84efe1-a5cf-476c-a774-66c102d50852"
}
```

3. **SORRY**

```json
{
  "type": "Song",
  "creator": "THISMINORITY",
  "file_name": "SORRY",
  "song_url": "https://open.spotify.com/track/0oJzHI9SKxu8wtpXotKSIp?si=4b13f34320d94889",
  "price": ".04 ETH (~$107)",
  "scarcity": "/ 100",
  "utility": "20% off live shows",
  "tags": ["HipHop"],
  "geo": "NYC",
  "image_url": "https://firebasestorage.googleapis.com/v0/b/mash-8645e.appspot.com/o/Mike%20Bellamy%20Music%2F9.CHK.jpg?alt=media&token=da84efe1-a5cf-476c-a774-66c102d50852"
}
```

4. **SUNNY BEACHES**

```json
{
  "type": "Song",
  "creator": "THISMINORITY",
  "file_name": "SUNNY BEACHES",
  "song_url": "https://open.spotify.com/track/0RW949RAywkEXhd2ckmdos?si=71efedb7caab4d9d",
  "price": ".04 ETH (~$107)",
  "scarcity": "/ 100",
  "utility": "20% off live shows",
  "tags": ["HipHop"],
  "geo": "NYC",
  "image_url": "https://firebasestorage.googleapis.com/v0/b/mash-8645e.appspot.com/o/Mike%20Bellamy%20Music%2F9.CHK.jpg?alt=media&token=da84efe1-a5cf-476c-a774-66c102d50852"
}
```

5. **JUST ME**

```json
{
  "type": "Song",
  "creator": "THISMINORITY",
  "file_name": "JUST ME",
  "song_url": "https://open.spotify.com/track/5CLmJsqASmsDDsidQ0w44a?si=48741864df7446bf",
  "price": ".04 ETH (~$107)",
  "scarcity": "/ 100",
  "utility": "20% off live shows",
  "tags": ["HipHop"],
  "geo": "NYC",
  "image_url": "https://firebasestorage.googleapis.com/v0/b/mash-8645e.appspot.com/o/Mike%20Bellamy%20Music%2F9.CHK.jpg?alt=media&token=da84efe1-a5cf-476c-a774-66c102d50852"
}
```

6. **LOVE**

```json
{
  "type": "Song",
  "creator": "THISMINORITY",
  "file_name": "LOVE",
  "song_url": "https://open.spotify.com/track/5JXygDoJD4A318WTxyFUEA?si=f790fc60f08e4436",
  "price": ".04 ETH (~$107)",
  "scarcity": "/ 100",
  "utility": "20% off live shows",
  "tags": ["HipHop"],
  "geo": "NYC",
  "image_url": "https://firebasestorage.googleapis.com/v0/b/mash-8645e.appspot.com/o/Mike%20Bellamy%20Music%2F9.CHK.jpg?alt=media&token=da84efe1-a5cf-476c-a774-66c102d50852"
}
```

7. **SHINE**

```json
{
  "type": "Song",
  "creator": "THISMINORITY",
  "file_name": "SHINE",
  "song_url": "https://open.spotify.com/track/7aU8aVIzYcgHqP0CwexcDp?si=22d2bbb3417a4374",
  "price": ".04 ETH (~$107)",
  "scarcity": "/ 100",
  "utility": "20% off live shows",
  "tags": ["HipHop"],
  "geo": "NYC",
  "image_url": "https://firebasestorage.googleapis.com/v0/b/mash-8645e.appspot.com/o/Mike%20Bellamy%20Music%2F9.CHK.jpg?alt=media&token=da84efe1-a5cf-476c-a774-66c102d50852"
}
```

 
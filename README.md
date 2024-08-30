cqlsh
CREATE KEYSPACE IF NOT EXISTS pop_music
   ... WITH replication = {'class': 'SimpleStrategy', 'replication_factor': 1};
USE pop_music;
CREATE TABLE IF NOT EXISTS pop_divas (
             ...     diva_id UUID PRIMARY KEY,
             ...     name TEXT,
             ...     debut_year INT,
             ...     genre TEXT
             ... );
cqlsh:pop_music> INSERT INTO pop_divas (diva_id, name, debut_year, genre) 
             ... VALUES (uuid(), 'Beyoncé', 1997, 'R&B');
cqlsh:pop_music> INSERT INTO pop_divas (diva_id, name, debut_year, genre) 
             ... VALUES (uuid(), 'Taylor Swift', 2006, 'Pop');
cqlsh:pop_music> 
cqlsh:pop_music> INSERT INTO pop_divas (diva_id, name, debut_year, genre) 
             ... VALUES (uuid(), 'Lady Gaga', 2008, 'Pop');
cqlsh:pop_music> 
cqlsh:pop_music> INSERT INTO pop_divas (diva_id, name, debut_year, genre) 
             ... VALUES (uuid(), 'Ariana Grande', 2013, 'Pop');
cqlsh:pop_music> 
cqlsh:pop_music> INSERT INTO pop_divas (diva_id, name, debut_year, genre) 
             ... VALUES (uuid(), 'Rihanna', 2005, 'Pop');
cqlsh:pop_music> CREATE TABLE IF NOT EXISTS albums (
             ...     album_id UUID PRIMARY KEY,
             ...     diva_id UUID,
             ...     album_name TEXT,
             ...     release_year INT,
             ...     total_sales INT
             ... );

CREATE TABLE IF NOT EXISTS albums (
             ...     album_id UUID PRIMARY KEY,
             ...     diva_id UUID,
             ...     album_name TEXT,
             ...     release_year INT,
             ...     total_sales INT
             ... );
cqlsh:pop_music> SELECT diva_id FROM pop_divas WHERE name = 'Beyoncé' ALLOW FILTERING;

 diva_id
--------------------------------------
 f82bfd07-12e5-49d0-b322-dcf9e76985ad

(1 rows)
cqlsh:pop_music> SELECT diva_id FROM pop_divas WHERE name = 'Taylor Swift' ALLOW FILTERING;

 diva_id
--------------------------------------
 b0d30edc-4435-4eaf-9367-d29bd0e38070

(1 rows)
cqlsh:pop_music> SELECT diva_id FROM pop_divas WHERE name = 'Lady Gaga' ALLOW FILTERING;

 diva_id
--------------------------------------
 e3f05995-3ea9-43d6-b611-58350107c610

(1 rows)
cqlsh:pop_music> SELECT diva_id FROM pop_divas WHERE name = 'Ariana Grande' ALLOW FILTERING;

 diva_id
--------------------------------------
 d7d8a75a-8401-492d-8fb0-0912c9511d07

(1 rows)
cqlsh:pop_music> SELECT diva_id FROM pop_divas WHERE name = 'Rihanna' ALLOW FILTERING;

 diva_id
--------------------------------------
 cf09d053-53ea-46a0-8b47-5be3d9443ca0

(1 rows)
cqlsh:pop_music> INSERT INTO albums (album_id, diva_id, album_name, release_year, total_sales) 
             ... VALUES (uuid(), f47ac10b-58cc-4372-a567-0e02b2c3d479, 'Lemonade', 2016, 5000000);
cqlsh:pop_music> 
cqlsh:pop_music> INSERT INTO albums (album_id, diva_id, album_name, release_year, total_sales) 
             ... VALUES (uuid(), f47ac10b-58cc-4372-a567-0e02b2c3d479, 'Dangerously in Love', 2003, 10000000);
cqlsh:pop_music> INSERT INTO albums (album_id, diva_id, album_name, release_year, total_sales) 
             ... VALUES (uuid(), 123e4567-e89b-12d3-a456-426614174001, '1989', 2014, 10000000);
cqlsh:pop_music> 
cqlsh:pop_music> INSERT INTO albums (album_id, diva_id, album_name, release_year, total_sales) 
             ... VALUES (uuid(), 123e4567-e89b-12d3-a456-426614174001, 'Red', 2012, 8000000);
cqlsh:pop_music> INSERT INTO albums (album_id, diva_id, album_name, release_year, total_sales) 
             ... VALUES (uuid(), 123e4567-e89b-12d3-a456-426614174002, 'The Fame', 2008, 15000000);
cqlsh:pop_music> 
cqlsh:pop_music> INSERT INTO albums (album_id, diva_id, album_name, release_year, total_sales) 
             ... VALUES (uuid(), 123e4567-e89b-12d3-a456-426614174002, 'Born This Way', 2011, 6000000);
cqlsh:pop_music> INSERT INTO albums (album_id, diva_id, album_name, release_year, total_sales) 
             ... VALUES (uuid(), 123e4567-e89b-12d3-a456-426614174003, 'Sweetener', 2018, 3000000);
cqlsh:pop_music> 
cqlsh:pop_music> INSERT INTO albums (album_id, diva_id, album_name, release_year, total_sales) 
             ... VALUES (uuid(), 123e4567-e89b-12d3-a456-426614174003, 'Thank U, Next', 2019, 4000000);
cqlsh:pop_music> INSERT INTO albums (album_id, diva_id, album_name, release_year, total_sales) 
             ... VALUES (uuid(), 123e4567-e89b-12d3-a456-426614174004, 'Anti', 2016, 5000000);
cqlsh:pop_music> 
cqlsh:pop_music> INSERT INTO albums (album_id, diva_id, album_name, release_year, total_sales) 
             ... VALUES (uuid(), 123e4567-e89b-12d3-a456-426614174004, 'Good Girl Gone Bad', 2007, 9000000);

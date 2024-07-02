# Music-Store Analysis
## Overview
This README file provides an overview of the Music Store Database project implemented using PostgreSQL. The database is designed to manage information about a music store, including details about artists, albums, tracks, genres, customers, invoices, and invoice items. The aim is to provide a comprehensive system for managing a music store's inventory and sales.

## Database structure
### Tables
The Music Store Database consists of the following tables:

#### Artist: Stores information about artists.
* ArtistId (Primary Key)
* Name
#### Album: Stores information about albums.
* AlbumId (Primary Key)
* Title
* ArtistId 
#### Track: Stores information about tracks.
* TrackId (Primary Key)
* Name
* AlbumId 
* MediaTypeId 
* GenreId 
* Composer
* Milliseconds
* Bytes
* UnitPrice
#### Genre: Stores information about genres.
* GenreId (Primary Key)
* Name
#### MediaType: Stores information about media types.
* MediaTypeId (Primary Key)
* Name
#### Customer: Stores information about customers.
* CustomerId (Primary Key)
* FirstName
* LastName
* Company
* Address
* City
* State
* Country
* PostalCode
* Phone
* Fax
* Email
* SupportRepId (Foreign Key)
#### Invoice: Stores information about invoices.
* InvoiceId (Primary Key)
* CustomerId (Foreign Key)
* InvoiceDate
#### Invoiceline: Stores information about invoice items.
* InvoiceLineId (Primary Key)
* InvoiceId (Foreign Key)
* TrackId (Foreign Key)
* UnitPrice
* Quantity
and a lot.
## Relationships
* Each artist can have multiple albums.
* Each album belongs to one artist and can have multiple tracks.
* Each track belongs to one album, one media type, and one genre.
* Each customer can have multiple invoices.
* Each invoice belongs to one customer and can have multiple invoice items.
* Each invoice item belongs to one invoice and one track.
## Usage
### Connecting to the Database
To connect to the database, use the following command:
psql -d music_store -U your_username
### Sample Queries
Here are some sample queries to interact with the database:

#### Get all artists:
SELECT * FROM Artist;
#### Get all albums by a specific artist:
SELECT * FROM Album WHERE ArtistId = 1;
#### Get all tracks in a specific album:
SELECT * FROM Track WHERE AlbumId = 1;
#### Get all invoices for a specific customer:
SELECT * FROM Invoice WHERE CustomerId = 1;
## Conclusion
The Music Store Database project is a robust system designed to manage a music store's inventory and sales information efficiently. By leveraging PostgreSQL, this database provides a reliable and scalable solution for storing and retrieving detailed information about artists, albums, tracks, genres, customers, invoices, and invoice items. Whether you're a developer looking to understand the database structure or a store owner aiming to manage your inventory and sales data, this project offers the tools and documentation needed to get started. Contributions and improvements to this project are encouraged to enhance its functionality and adapt it to various use cases. Thank you for using the Music Store Database!

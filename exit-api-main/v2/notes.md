# Notes for the split approach

- Don't think of it as two separate APIs, but rather two different ways to consume the same data.
- It's one API, but with two different endpoints to provide the data in two different formats.
- Caters to different use cases, one for databases and one for frontends.

## How partners could use the API
- Partners who want to populate their own databases with LVC data will use the traditional API endpoint.
- Partners who want to inject JSON-LD onto their website will use the JSON-LD endpoint to add the JSON to their databases, and then inject the JSON-LD onto their website.

ex: 
### Partner who only wants data for their database
- Partner can populates their database using full data endpoint. From their they are free to use the data as they see fit.

### Partner who wants JSON-LD
- Partners can use the JSON-LD endpoint to populate their database with JSON-LD. They can then inject the JSON-LD directly onto their website.
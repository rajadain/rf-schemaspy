# Raster Foundry Database Schema

Database Schema for [Raster Foundry](https://github.com/azavea/raster-foundry)

To generate this schema, do the following:

 * Download [schemaspy](https://github.com/schemaspy/schemaspy)
 * Download the [Postgres JBDC driver](https://jdbc.postgresql.org/download.html)

Ensure the database is accessible at `tcp://localhost:5432`.
You may have to map ports in `docker-compose.yml` as well as expose the port in Vagrant.

Then, assuming both files are available in the same directory, run the following command:

```bash
$ java -jar schemaspy-6.0.0-beta.3.jar -t pgsql -dp postgresql-42.0.0.jar \
       -s public -host localhost -renderer :quartz \
       -o $OUTPUT_DIR -db $RF_DBNAME -u $RF_DBUSER -p $RF_DBPASS
```

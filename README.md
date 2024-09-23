Instructions for Running the Project


To use this project correctly, follow these steps:

Navigate to the project's root directory.

Run the following command to start the Docker containers:
```
docker compose up
```
This command will pull three images: Postgres, Kafka, and Zookeeper.

After the Posgres is ready, please use the SQL below to create the table PROPERTIES and insert some dummy properties into it:

```sql
CREATE TABLE properties (
    id SERIAL PRIMARY KEY,
    CREATED_ON TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    APPLICATION VARCHAR(255),
    PROFILE VARCHAR(255),
    LABEL VARCHAR(255),
    PROP_KEY VARCHAR(255),
    VALUE VARCHAR(255)
);

INSERT INTO properties (APPLICATION, PROFILE, LABEL, PROP_KEY, VALUE) VALUES
    ('spring-cloud-config-client', 'dev', 'latest', 'URL_A', 'https://client-urlA-dev.com'),
    ('spring-cloud-config-client', 'dev', 'latest', 'URL_B', 'https://client-urlB-dev.com'),
    ('spring-cloud-config-client', 'test', 'latest', 'URL_A', 'https://client-urlA-test.com'),
    ('spring-cloud-config-client2', 'dev', 'latest', 'URL_A', 'https://client2-urlA-dev.com'),
    ('spring-cloud-config-client2', 'test', 'latest', 'URL_A', 'https://client2-urlA-test.com');
```

After that start the server project.

Then, run the client project.

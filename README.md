# OS.js v3 Database Auth Docker Example

This example runs on docker and demonstrates the database authentication adapter.

First set up database:

```bash
docker-compose up db

echo "CREATE DATABASE osjsv3;" | docker-compose exec db mysql -uroot -psecret
echo "CREATE USER 'osjsv3'@'localhost' IDENTIFIED BY 'secret';" | docker-compose exec db mysql -uroot -psecret
echo "GRANT ALL ON osjsv3.* TO 'osjsv3'@'localhost';" | docker-compose exec db mysql -uroot -psecret
```

Then start servers and add your user. Note that the first time this is run it might take a while.

```bash
docker-compose up

docker-compose exec osjs npx osjs-cli user:add --username=name --groups=admin
```

In the future you can just use `docker-compose up` to start everything.

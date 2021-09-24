# Launch the MongoDB Server container. A docker network ass1 will be created.
docker-compose up

# Launched a bash shell  into mongodb container and check that the database and collections are initialized
docker exec -it db bash

mongo -u comp3122 -p 12345
show dbs;
use university
show collections;
db.student.find()
db.takes.find({})

# Stop and remove mongodb container and volumes
docker-compose down -v


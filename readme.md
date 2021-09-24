# Launch the MongoDB Server container. A docker network ass1 will be created.
docker-compose up

# launched a bash shell  into mongodb container and check that the database and collections are initialized
docker exec -it db bash

mongo -u comp3122 -p 12345
show dbs;
use university
show collections;
db.student.find()
db.takes.find({})

# Stop and remove all containers and volumes
docker-compose down -v

# Launch python flask app
docker run --rm --network ass1 -e  MONGO_USERNAME=comp3122 -e  MONGO_PASSWORD=12345 -e MONGO_SERVER_HOST='mongo' -e MONGO_SERVER_PORT='27017' -p 9990:15000 cswclui/student_svc

# Local MongoDB Instance (with authentication)
    docker run --name mongo-db -p 27017:27017/tcp \ 
    -e MONGO_INITDB_ROOT_USERNAME=admin \
    -e MONGO_INITDB_ROOT_PASSWORD=example -d mongo


# Access to MongoDB Instance
    mongodb://admin:example@localhost:27017

# MongoDB Sample Data Import
    mongo

    use admin

    db.auth("admin","example")

    db.createUser({user:"restore",pwd:"restore",roles:["restore"]})

    exit

    apt update

    apt install wget

    wget https://atlas-education-staging.s3.amazonaws.com/sampledata.archive.gz

    mongorestore --username restore --password restore --authenticationDatabase admin --gzip --archive=sampledata.archive.gz

    rm sampledata.archive.gz




# docker-tester-spring-files
A demo docker-compose to run a spring server that manage files and an e2e tester for it.

### docker-compose files
1. docker-compose-local-temp.yml: use local dir in the server to store files and Java in memory map to store metadata.
2. docker-compose-redis-redis.yml: Use Redis DB, running in Docker, to store both files content and metadata.
3. docker-compose-local-hadoop.yml: Use Hadoop, running in Dockers (nodename and datanode) to store file content and Java in memory map to store metadata.
4. docker-compose-redis-hadoop.yml: Use Hadoop, running in Dockers (nodename and datanode) to store file content and Redis DB, in Docker, to store metadata.

### Related projects

1. [springboot-files-storage](https://github.com/orbartal/springboot-files-storage):

A demo of a springboot universal file storage service to upload and download files with uid and metadata.

The file service can use different DBs to store its files content and metadata. It depend on its environment variables in the docker-compose.

2. [springboot-files-storage-tester](https://github.com/orbartal/springboot-files-storage-tester):

A tester that enable to run e2e test of upload and download a file (using same UID for both actions):

3. [docker-tester-spring-files](https://github.com/orbartal/docker-tester-spring-files):

A docker-compose that enable to run the target serivce with different config properties and supporting DBS.

And that allow the tester to test the service while its using the different config and DBS options. 

Note: The target details code and DB are transparent to the tester who only knows about the API contract.


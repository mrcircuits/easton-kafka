# easton-kafka
a 3 broker kafka, 1 zookeeper, &amp; a http server contained in a docker compose file

install docker compose on your system, https://docs.docker.com/compose/install/#prerequisites


To use, edit the docker-compose.yml file and replace the 3 instances 
"KAFKA_ADVERTISED_HOST_NAME:" with your ip address (not 127.0.0.1 or localhost) i.e. 192.168.3.29

run the command the following command in the same directory as above: docker-compose up -d

The kafka servers should now be running, along with the HTTP server.

To connect a kafka producer/consumer, use the bookstrap_servers: "'your ip address':9092,'your ip address':9091,'your ip address':9093" 

To connect to the http producer, use send a post to 'your ip address':8081, 
with the headers 'Device-Id' & 'Data-Type'

You may need to setup your firewall to allow these ports through

To close the kafka servers & http server, use: docker-compose down

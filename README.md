## Docker ELK stack

Run the latest version of the ELK (Elasticseach, Logstash, Kibana) stack with Docker and Docker-compose.

It will give you the ability to analyze any data set by using the searching/aggregation capabilities of Elasticseach and the visualization power of Kibana.

Based on the official images:

   * [elasticsearch](https://hub.docker.com/_/elasticsearch/)
   * [logstash](https://hub.docker.com/_/logstash/)
   * [kibana](https://hub.docker.com/_/kibana/)


### Prerequisites

Create a EC2 with docker server running
	
	https://aws.amazon.com/
	
Install Docker Server with support compose
 
 	https://www.docker.com
 	wget -qO- https://get.docker.com/ | sh
	sudo usermod -aG docker ubuntu
	
 	curl -L "https://github.com/docker/compose/releases/download/1.8.1/docker-compose-$(uname -s)-$(uname -m)" > /usr/local/bin/docker-compose

 	chmod +x /usr/local/bin/docker-compose
 			

### Installing

  	git checkout https://github.com/fdnascimento/docker-elk.git  
  	docker-compose up -d
  	
  	For more information about docker-compose use docker-compose --help


### Running the tests

	Create a new app rails set set some configurations in config/evironments/pruduction.rb
	Add this line on end file.
	 		 
	config.logger = ActiveSupport::Logger.new(STDOUT)    
   	config.lograge.enabled = true
   	config.lograge.formatter = Lograge::Formatters::Logstash.new

	docker run --name servicename -d -p 8080:8080 --log-driver=gelf --log-opt gelf-address=udp://localhost:12201 m4u:docker_image
	
Kibana <http://localhost:5601>

## Deployment



## Contributing
	
Leonardo Bernardelli <https://bitbucket.org/lbernardelli/elk-docker>


## Authors

* **Denis Nascimento** 


# Use and deploy this stack
To run it, you need Docker >= 1.10, and docker-compose

## Clone this repo with submodules
```
git clone --recursive https://github.com/RSNA/s4s-stack
```
### Update submodules after git pull

```
git submodule update --init --recursive
```

### Pull or build

```
docker-compose build # build the images yourself
# *or* ...
docker-compose pull  # pull the images from Docker Hub
```

# Configure and run locally

Edit `docker-compose.override.yml` and `docker-compose.loaddata.yml` as needed to configure your preferred local port and volume mappings. 

To launch the stack:
```
docker-compose up
```

Wait for the services to install then load sample data.
```
docker-compose -f docker-compose.loaddata.yml up
```

By default, you'll have servers running at ports:

 * `389`: LDAP server
 * `5432`: Postgres
 * `9990`: Wildfly Administration Console
 * `9090`: Archive console
 * `11112`: dcm4chee server (SCP)
 * `2575`: HL7 server
 * `4567`: DICOM-RS Broker service
 * `11122`: DICOM-RS Broker SCP
 * `9004`: Introspection service
 
and mappings to the host filesystem:

 * `/etc/localtime`: Sync the time with the host machine
 * `/var/local/dcm4chee-arc/ldap`: LDAP data directory
 * `/var/local/dcm4chee-arc/db`: Postgres data directory
 * `/var/local/dcm4chee-arc/wildfly`: Wildfly directory
 * `/var/local/dcm4chee-arc/storage`: Dicom storage
 * `/var/local/dcmrs-broker/cache`: Cache directory for RS Broker
  
# Running tests
 
  To test the stack, refer to the [s4s-fhir-broker project](https://github.com/RSNA/s4s-fhir-broker#running-tests).
  
# Update submodules to latest on GH branches
```
git submodule update --remote
```


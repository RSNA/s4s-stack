# Use and deploy this stack
To run it, you need Docker >= 1.10, and docker-compose

## Clone this repo with submodules

git clone --recursive https://github.com/RSNA/s4s-stack

### Update submodules after git pull

```
git submodule update --init --recursive
```

### Pull or build

```
docker-compose build # build the images yourself #not completely working use pull
# *or* ...
docker-compose pull  # pull the images from Docker Hub
```

### To run or stop
```
docker-compose up
docker-compose down
```
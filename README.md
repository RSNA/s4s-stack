# Use and deploy this stack
To run it, you need Docker >= 1.10, and docker-compose

## Clone this repo with submodules

git clone --recursive https://github.com/s4s-stack

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

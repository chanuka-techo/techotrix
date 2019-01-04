# Techotrix

Lifted from [chanux/adventure-go](https://github.com/chanux/adventure-go)

Build as follows

    go build -o goadv techotrix.go

Run as follows

    ./techotrix

Check it as follows

    wget -qO - localhost:9000

    curl localhost:9000

    http --stream localhost:9000 # using python HTTPie

Static build

    CGO_ENABLED=0 go build -o bin/techotrix -a -ldflags '-s' techotrix.go

I build it with static linking to put it in a docker image.

Build docker image as follows

    docker build -t asia.gcr.io/silver-lead-205101/techotrix .

Run docker container as follows (This works even if you didn't build since I've
pushed [my image](https://registry.hub.docker.com/u/chanux/advgo/) to docker
hub)

    docker run -it --rm -p 9000:9000 asia.gcr.io/silver-lead-205101/techotrix

You can check it as same as before.

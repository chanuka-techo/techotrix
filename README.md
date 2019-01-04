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

If you are building on a mac >_<

    env CGO_ENABLED=0 GOOS=linux GOARCH=amd64 go build -o bin/techotrix -a -ldflags '-s' techotrix.go

I build it with static linking to put it in a docker image.

Build docker image as follows

    docker build -t chanuka_techo/techotrix .

And run..

    docker run -it --rm -p 9000:9000 chanuka_techo/techotrix

To test

    curl localhost:9000

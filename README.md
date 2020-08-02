# go-mp3-podcast

This is a fork of [go-mp3-podcast](https://github.com/rosmo/go-mp3-podcast).  The main changes so far have been to make the repository retrievable using `go get`.

This is an utility to take a directory containing MP3s and turn them into an
RSS feed. The utility is configured using a simple YAML file (see config.yml
for example).

## How to build with docker
```bash
docker run --rm -ti -v "$PWD":/usr/src/myapp -w /usr/src/myapp golang:1.14 bash -C \
       "go get github.com/kesha/go-mp3-podcast && \
       go install github.com/kesha/go-mp3-podcast && \
       cp /go/bin/go-mp3-podcast ."
docker rmi -f golang:1.14
chmod +x go-mp3-podcast
```

## How to build

You should be able to download, build, and install using:

`go get github.com/kesha/go-mp3-podcast`

and then

`go install github.com/kesha/go-mp3-podcast`

which will place the `go-mp3-podcast` binary in `$GOPATH/bin`.

## How to run

### RSS mode

```
go-mp3-podcast -config config.yml -dir /path/to/mp3s -mode rss
```

### Directory index mode

```
go-mp3-podcast -config config.yml -dir /path/to/mp3s -mode index
```

## License

Licensed under MIT. Copyright 2017 Taneli Leppä <rosmo@rosmo.fi>

## Acknowledgements

Uses great libraries from:
- [eduncan911/podcast](https://github.com/eduncan911/podcast)
- [mikkyang/id3-go](https://github.com/mikkyang/id3-go)

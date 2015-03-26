# Docker Exec Image: Racket

A Dockerfile describing an container capable of executing Racket source files.

# Build

```sh
git clone https://github.com/docker-exec/racket.git
docker build -t dexec/racket .
```

# Usage

In a directory containing a script e.g. foo.rkt, run:

```sh
docker run -t --rm \
    -v $(pwd -P)/foo.rkt:/tmp/dexec/build/foo.rkt \
    dexec/racket foo.rkt
```

## Passing arguments to the script

Arguments can be passed to the script using any of the following forms:

```
-a argument
--arg argument
--arg=argument
```

Each argument passed must be prefixed in this way, e.g.

```sh
docker run -t --rm \
    -v $(pwd -P)/foo.rkt:/tmp/dexec/build/foo.rkt \
    dexec/racket foo.rkt \
    --arg='hello world' \
    --arg=foo \
    --arg=bar
```

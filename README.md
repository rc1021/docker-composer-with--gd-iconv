# docker-composer-with-gd

Docker build for php composer with gd

## usage

**build**
```
$ cd 1.8
$ docker build -t "composer--gd-iconv:1.8" .
```

**composer install**
```
$ docker run --rm --interactive --tty \
  --volume $PWD:/app \
  composer--gd-iconv:1.8  install --prefer-dist --no-scripts --no-dev
```

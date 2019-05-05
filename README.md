# docker-composer-with-gd

Docker build for php composer with gd

## usage

```
$ docker run --rm --interactive --tty \
  --volume $PWD:/app \
  composer--gd-iconv:1.8  install --prefer-dist --no-scripts --no-dev
```
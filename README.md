# StoRM Docker© deployment tests

### Build images

Images are automatically downloaded from docker-hub during execution.

If you need to locally build them:

- **italiangrid/storm-testsuite**

```
cd docker
cd storm-testsuite
sh build-image.sh
```

- **italiangrid/storm-deployment**

```
cd docker
cd storm-deployment
sh build-image.sh
```

### Usage

Edit as your needed `.env` files:

```
$ cat docker/storm-testsuite.env
TESTSUITE_BRANCH=master
TESTSUITE_EXCLUDE=to-be-fixedORno-btrfsORcdmi
```

```
$ cat docker/storm-deployment.env
STORM_DEPLOYMENT_TEST_BRANCH=release_1_11_13
MODE=clean
PLATFORM=centos6
```

**Launch**

Run deployment using docker-compose:

```
$ cd docker
$ docker-compose up -d
```

Check logs:

```
$ docker-compose logs -f
$ docker-compose logs -f docker-storm
$ docker-compose logs -f docker-storm-testsuite
```

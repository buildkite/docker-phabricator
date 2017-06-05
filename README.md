docker-phabricator
==================

A local Dockerized version of Phabricator for developing and testing the Buildkite integration, and developing new changes for our [buildkite-patches branch of Phabricator](https://github.com/buildkite/phabricator/tree/buildkite-support).

Originally forked from the now unmaintained https://github.com/yesnault/docker-phabricator.

## Setup

```bash
docker-compose up
echo '8081' > '~/.pow/phabricator'
open http://phabricator.dev/
```

## Developing Phabricator

To run your own version, make sure phabricator is checked out:

```bash
git checkout -b buildkite-support git@github.com:buildkite/phabricator.git
```

And then run the `dev` version of the docker-compose config:

```bash
docker-compose -f docker-compose.yml -f docker-compose.dev.yml up
```

This will link in the local Phabricator source as a volume, so you can easily edit + test changes to Phabricator.

If you need to use bash in the Phabricator container:

```bash
docker-compose -f docker-compose.yml -f docker-compose.dev.yml run phabricator bash
```

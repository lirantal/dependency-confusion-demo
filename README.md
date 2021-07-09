## Exercise

Begin by having a local copy of the verdaccio npm local proxy.

Using Docker is an easy way to spin it up quickly:

```sh
docker run -it --rm --name verdaccio -p 4873:4873 verdaccio/verdaccio
```

We then create a local npm proxy user, and publish the legitimate `the-superlaser` package to it:

```sh
npm adduser --registry http://0.0.0.0:4873
```

Followed by:

```sh
cd packages/the-superlaser
npm publish --registry http://0.0.0.0:4873
```


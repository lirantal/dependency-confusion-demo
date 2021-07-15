## Exercise

### Local npm private proxy setup

Begin by having a local copy of the verdaccio npm local proxy.

Using Docker is an easy way to spin it up quickly:

```sh
docker run -it --rm --name verdaccio -p 4873:4873 verdaccio/verdaccio
```

We then create a local npm proxy user, and publish the legitimate `the-superlaser` package to it:

```sh
npm adduser --registry http://0.0.0.0:4873
```

```sh
npm login --registry http://0.0.0.0:4873
```

### Publish a private npm package

Your own `superlaser`, push it to the registry:

```sh
cd packages/superlaser
npm publish --registry http://0.0.0.0:4873
```

Install this package in a project. You get that 1.0.0 version. Great.

Now, push a package of the same name to npmjs, with a higher version range: 1.999.99. Then install the package in a new project. What happens?
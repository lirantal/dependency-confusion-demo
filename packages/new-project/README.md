To demonstrate the default behavior of private npm registries and proxies go ahead and run the following:

1. Init a new npm project: `npm init -y`
2. Install the package name that is used internally: `npm install superlaser`, assuming that its name is `superlaser` and that the public npm package registry holds a newer version, such as `superlaser@999.99.99`

The end result is the malicious version `superlaser@999.99.99` being fetched and installed.
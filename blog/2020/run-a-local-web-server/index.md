# Run A Local Web Server

April 2, 2020 by [Areg Sarkissian](https://aregsar.com/about)

If you have NodeJS installed you can use the npx cli.

```bash
# serve files from the current directory
npx serve .
```

If you have PHP installed you can use the php cli.

```bash
# serve files from the current directory and tail the web server output
php -S localhost:5000 -t .
```

If you have Python 3 installed you can use the python cli.

```bash
# serve files from the current directory
python3 -m http.server
```

## Serving using ParcelJS

If you want to bundle code before serving, you can use the ParcelJS bundler from `https://parceljs.org/`

### Setup ParcelJS using NPM

If you have node installed you can install ParcelJS globally using the npm cli.

```bash
npm install -g parcel-bundler
```

You need to create a project directory and initialize it:

```bash
mkdir myproject && cd myproject
# create a package.json file
npm init -y
```

Once initialized you can run the server using the parcel cli.

```bash
parcel index.html -p 5000
```

### Setup ParcelJS using YARN
If you have node installed and you installed the yarn package manager, you can install ParcelJS globally using the yarn cli.

```bash
yarn global add parcel-bundler
```

You need to create a project directory initialize it:

```bash
mkdir myproject && cd myproject
# create a package.json file
yarn init -y
```

Once initialized you can run the server using the parcel cli.

```bash
parcel index.html -p 5000
```

## Testing the local web server

Add index.html file in the directory that you run the local server and add the following html content into it:

```html
<html>
<body>
Hello
</body>
</html>
```

Here is how you can do this using a bash script:

```bash
touch index.html
echo '<html><body>Hello</body></html>' > index.html
```

Now run any of the server execution scripts mentioned in this article to serve up `index.html` the file.

Navigate your browser to `http://localhost/index.html` to view the file.

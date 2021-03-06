<div align='center'>
  <br />
  <p>
    <img src='media/kirb.gif' /><h1 style='font-size:107px;'>Kirbe</h1>
  </p>
  <br />
  <p>
    <a href='https://packagephobia.now.sh/result?p=kirbe'><img src='https://packagephobia.now.sh/badge?p=kirbe' alt='Install Size' /></a>
    <a href='https://discord.gg/SV7DAE9'><img src='https://discordapp.com/api/guilds/107131083958538240/embed.png' alt='Discord' /></a>
    <a href='https://www.npmjs.com/package/kirbe'><img src='https://img.shields.io/npm/v/kirbe.svg?maxAge=3600' alt='NPM version' /></a>
    <a href='https://www.npmjs.com/package/kirbe'><img src='https://img.shields.io/npm/dt/kirbe.svg?maxAge=3600' alt='NPM version' /></a>
    <a href='https://www.patreon.com/wessel'><img src='https://img.shields.io/badge/donate-patreon-F96854.svg' alt='Patreon' /></a>
  </p>
  <p>
    <a href='https://nodei.co/npm/kirbe/'><img src='https://nodei.co/npm/kirbe.png?downloads=true&stars=true' alt='npm installnfo' /></a>
  </p>
</div>

> A lightweight and fast Node.js HTTP server library

> [GitHub](https://www.github.com/PassTheWessel/kirbe) **|** [NPM](https://www.npmjs.com/package/kirbe)

## Installing
```sh
$ yarn add kirbe # Install w/ Yarn (the superior package manager)
$ npm i kirbe # Install w/ NPM
```

## Usage
#### Start a HTTP(s) server on port 8080 and add some routes
```js
const kirbe = require('kirbe'); // Define kirbe

const app = new kirbe.Server(); // Make your kirbe instance

app.route('/bear', 'GET', (req, res) => res.status( 200 ).body({'bear': 'cop'}));
app.route((req, res) => res.status(404).body('Error: Content not found!').end());
app.get('/kirb', (req, res) => {
  res.writeHead(201, {'test': 'hi'});
  res.end({'key': 'hi'});
});

// HTTP
app.listen(8080, () => console.log('Listening on port 8080!'));
// HTTPS
const https = require('https'); // This should be at the top of your code
https.createServer(app.externalHandler).listen(8080);
```

## Default extensions ( [/model/middleware](model/middleware) )
#### Static
Host static files on your website
##### Usage
```js
const path  = require('path'); // Define path
const kirbe = require('kirbe'); // Define kirbe

const app = new kirbe.Server(); // Make your kirbe instance

app.use(kirbe.Static(path.join(__dirname, 'static')));
```

### Creating your own
If you want to add your own extension/middleware, you can either create your own module or add it to the [/model/middleware](model/middleware) and then create a pull request!

### Why use kirbe?
Kirbe is a lightweight and fast HTTP server library, especially comparing to express and connect which are around 1mb in size with multiple dependencies. If you want any features that aren't inside of Kirbe yet, you can open an issue or pull request.

You can join [https://discord.gg/SV7DAE9](https://discord.gg/SV7DAE9) if you need any support using kirbe!

# A Guide to three.js

## Setup

There are two different ways to setup `three.js` on your system, but in this guide, we are going to be doing it via `NPM`.

### Node.js

Before we get started, make sure you have `Node.js` installed. 

If you are not sure if you have `Node.js`, you can check with the following command in your terminal:

```shell
node --version
```

If you get a version number, then, you have `Node.js` installed. if not, you will need to install it. You can find a guide to setting `Node.js` here: [Guide to set up Node.js](https://github.com/refiloemopeloa/Guides/blob/main/Web%20Development/JS/Node.js.md)

### three.js

Once you have `Node.js`, we can begin the setup for `three.js`:

You need to install three.js in the directory you'll be working from. Create a directory then open the terminal in that directory. Then we need to set our project structure.

#### Project Structure

Every `three.js` project needs at least one `HTML` file to define the webpage, and a `JavaScript` file to run your `three.js` code. The structure and naming choices below aren't required, but for the sake of consistency throughout this guide, we'll make use of them. Create a directory and add the following files:

##### index.html

The `index.html` file defines the webpage. Add the following boiler plate to your file:

```html
<!DOCTYPE html> 
<html lang="en"> 
	<head> 
		<meta charset="utf-8"> 
		<title>My first three.js app</title> 
		<style> body { margin: 0; } </style> 
	</head> 
	<body> 
		<script type="module" src="/main.js"></script> 
	</body> 
</html>
```

##### main.js

The `main.js` file is where our `three.js` code is run. For now, you only need to import the `three.js` libraries into your file:

```js
import * as THREE from 'three';
```

##### public directory

The `public` folder is sometimes also called a `static` folder. It contains files that are pushed to the website unchanged. Usually textures, audio, and 3D models will go here. 

Now that we've completed the project structure, let us begin with the setup.

#### Installation

Open your terminal in the folder where you added the above files. Then:
1. Run the following commands:
```shell
# three.js 
npm install --save three

# vite 
npm install --save-dev vite
```

##### Why Vite?

Basically, `Vite` improve the server start time by dividing the modules in an application into `dependencies` and `source code`, then serves the `source code` over `native ESM`. Without getting too technical, `Vite` reduces the time it takes for our server to start.

 When `Vite` builds your application, it sees imports for 'three' and pulls three.js files automatically from this folder.

##### Note of version history

The `node_modules` folder is used only during development, and shouldn't be uploaded to your web hosting provider or committed to version history. In other words, add it to your `ignore` file.

#### Running

To run your app, type:

```shell
npx vite
```

##### What is `npx`?

`npx` is installed with Node.js, and runs command line programs like `Vite` so that you don't have to search for the right file in `node_modules` yourself.

##### Running with `npm run dev`

If you prefer, you can put following into the `package.json:scripts` list, and use `npm run dev` instead:

```json
"scripts": { 
	"dev": "vite", // start dev server, aliases: `vite dev`, `vite serve` 
	"build": "vite build", // build for production 
	"preview": "vite preview" // locally preview production build 
}
```

##### Success?

If everything went well, you should see something like:

```shell
  VITE v5.4.8  ready in 346 ms

  ➜  Local:   http://localhost:5173/
  ➜  Network: use --host to expose
  ➜  press h + enter to show help
```

Open the local link to a blank page and, well, you've done it! Congratulations, you're now ready to make some amazing visuals.
# References 

1. [three.js docs (threejs.org)](https://threejs.org/docs/index.html#manual/en/)
2. [Why Vite | Vite (vitejs.dev)](https://v3.vitejs.dev/guide/why.html)
3. [Getting Started | Vite](https://vite.dev/guide/#command-line-interface)
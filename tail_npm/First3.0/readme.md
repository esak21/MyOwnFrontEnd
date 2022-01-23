# Install Tailwind using npm 
`npm init` 

it will generate a package.json File 

## install tailwind Project 
`npm install -D tailwind`

## intiate the tailwind project 
`npx tailwindcss init -p ` <br>

``    Created Tailwind CSS config file: tailwind.config.js
    Created PostCSS config file: postcss.config.js``
## Update the location in which our HTML file is available 
```
  content: ["./src/**/*.{html,js}"],
```

## create Src and index.html File 

## Create Script in package Json File 
      "scripts": {
        "tailwind:build:dev":"npx tailwindcss -i style.css -o ./src/style.css --watch"
        },

    ## Add a Server

    npm install -D servor npm-run-all

## update the SCript 
`npm run dev `


## Add purging to remove unwanted css 
`npm install -D postcss-cli autoprefixer cssnano `

## Updated package.json
```
{
  "name": "first3.0",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "tailwind:build:dev": "npx tailwindcss -i style.css -o ./src/style.css --watch",
    "tailwind:build:prod": "postcss  style.css -o ./src/style.css ",
    "server": "servor src index.html 8060 --browse --reload",
    "dev": "run-p \"tailwind:build:dev\" \"server\" ",
    "prod": "npm run tailwind:build:prod"
  },
  "author": "",
  "license": "ISC",
  "devDependencies": {
    "autoprefixer": "^10.4.2",
    "cssnano": "^5.0.15",
    "npm-run-all": "^4.1.5",
    "postcss-cli": "^9.1.0",
    "servor": "^4.0.2",
    "tailwindcss": "^3.0.15"
  }
}


```

## updated postcss.config.js
```
module.exports = {
  plugins: {
    tailwindcss: {},
    autoprefixer: {},
    cssnano:{}
  },
}

```

## updated tailwind config 

```
module.exports = {
  content: ["./src/**/*.{html,js}"],
  theme: {
    extend: {},
  },
  plugins: [],
}

```
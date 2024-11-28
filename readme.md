# How to setup express in ts
1) create main.js
2) npm init -y
3) npm i express
4) npm i typescript nodemon @types/express @types/node -D
5) tsc --init
6) change main.js to main.ts
7) uncomment "outDir": "./dist" and "rootDir": "./src" in the tsconfig.json
8) create src dir and move main.ts into src.    src/main.ts
9) npm i rimraf concurrently
10) add this commands in package.json


	       "scripts": {
	    
			    "prebuild": "rimraf ./dist",
			    
			    "build": "npx tsc",
			    
			    "start": "node ./dist/main.js",
			    
			    "preserve": "npm run build",
			    
			    "serve": "concurrently \"npx tsc -w\"  \"nodemon ./dist/main.js\"",
			    
			    "test": "echo \"Error: no test specified\" && exit 1"
	    
	    },

11) npm run serve 

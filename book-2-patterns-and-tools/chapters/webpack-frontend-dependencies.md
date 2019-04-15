# Configuring Frontend Dependencies with Webpack

## Installing Regular Dependencies
To install the front-end dependences run the following:
```sh
npm install bootstrap jquery popper.js --save
```
You should now see these three packages under the dependencies object in the package.json file.  Our package.json file knows to save this stuff as regular dependencies because of the `--save` flag at the end of the line.

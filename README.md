# Readme
Application code used for the github wiz halftime demo

You will need gulp installed to build this

Run npm install to pull gulp packages, then install the CLI:

```bash
npm install --global gulp-cli
```

Then to build and run the app:
```bash
gulp
node dist/app.js
```

View in browser:
```bash
http://localhost:3000
```

And to test built version in a container locally:

```bash
gulp docker
```

View in browser:
```bash
http://localhost:3000
```

## Project structure:
This is a deployable Docker application, with a Gulp setup that is designed to package a standalone website, install its dependencies, and run it inside a Docker container. When installed locally, there will be two different node modules folders, with their purpose detailed below:

### Root node_modules (Local Development & Build Tools):
Contains: Build tools (gulp, gulp-uglify, imagemin, del) alongside your app's dependencies.
Purpose: Runs locally on your machine so you can execute npx gulp, develop features, or test node app.js directly in your source folder.

### Dist node_modules (Docker Container Runtime):
Contains: The dependencies installed specifically inside the output directory by Gulp's npmInstall step.
Purpose: Serves as the isolated runtime environment bundled directly into your Docker container image.
Note: Because /dist contains the compiled code, static assets, Dockerfile, and its own node_modules, Docker treats /dist as a completely self-contained application bundle. It pulls only those production assets into the image, leaving your local development tools and root files behind.

# Setup
Setup instructions from Wiz Code Lab

1. Create new public repo in GitHub

2. Clone repo locally and create new branch

3. Copy application code to folder and run it:

```bash
curl -o githubhalftime.zip "https://rick-holding.s3.amazonaws.com/halftime/githubhalftime.zip"
unzip githubhalftime.zip -d .
rm githubhalftime.zip
```

Then build and test the app:
```bash
npm install
node app.js
```

View in browser:
```bash
http://localhost:3000
```
# Publishing Create-React-App on GitHub Pages

### Overview

This guide was written to help my fellow students upload and publish their Create-React-App onto GitHub Pages.

### Table of Contents

- Part 1 - [Syncing 'Create-React-App <App Name>' with GitHub Repository](#part-one)
- Part 2 - [Publishing 'Create-React-App <App Name>' onto GitHub Pages](#part-two)

### Part 1 - <a name="part-one"></a>Syncing 'Create-React-App <App Name>' with GitHub Repository

Step 1: CD into your react app folder and `git init`

Step 2: Whether your freshly create a react app folder or you’re working on your app, always a good idea to `git add <file(s)>` and `git commit -m <message in quotes>`

Step 3: Visit github.com and hit `+` > `New repository` in the upper right corner. Enter the name of your app folder under `Repository Name`, and DO NOT _Initialize this repository with a README_. Instead click the green `Create repository` button.

Step 4: Copy the `git remote add origin git@github.com:<username>/<repo>.git` and paste it in your terminal. Hit enter, then `git push -u origin master`

Step 5: If you’re still working, please do so and commit often. If you’re done with the assignment. Proceed to Part II if needed.

### Part 2 - <a name="part-two"></a>Publishing 'Create-React-App <App Name>' onto GitHub Pages

Step 1: CD into your react app folder if you haven’t already.

Step 2: In VS Code explorer (that left side viewer that shows your files and folders), locate your package.json and double-click to open. We’re going to make some edits.

Step 3: Somewhere in the package.json, you will need to enter the following line.

  ```"homepage": "https://<username>.github.io/<repo-name>",```

Here is a visual aide:

```...
"private": true,
"homepage": "https://julienshim.github.io/clicky-game",
"dependencies": {
...``` 

I personally put it between private and dependencies as shown above. Wherever your put it, make sure you’re mindful of the commas.

Step 4: Back in your terminal, enter the following command: `yarn add gh-pages` (why not, because we used yarn, but you can alternatively use `npm install --save gh-pages`

Step 5. Back to your package.json, make sure you have the following under “scripts” after the opening {

```"predeploy": "npm run build",
"deploy": "gh-pages -d build",```

In context, your package.json should look something like this in the end:

```{
  "name": "clicky-game",
  "version": "0.1.0",
  "private": true,
  "homepage": "https://julienshim.github.io/clicky-game",
  "dependencies": {
    "gh-pages": "^1.2.0",
    "react": "^16.4.1",
    "react-dom": "^16.4.1",
    "react-scripts": "1.1.4"
  },
  "scripts": {
    "predeploy": "npm run build",
    "deploy": "gh-pages -d build",
    "start": "react-scripts start",
    "build": "react-scripts build",
    "test": "react-scripts test --env=jsdom",
    "eject": "react-scripts eject"
  }
}```

Step 6: Enter the following in your terminal: `npm run deploy`

Step 7: Head back to your repo. Click `Settings` and under `GitHub Pages` confirm that your React App is published.

Step 8: Might as well submit your links to bootcampspot. (edited)
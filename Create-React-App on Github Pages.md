# Publishing Create-React-App on GitHub Pages

### Overview

This guide was written to help my fellow students upload and publish their Create-React-App onto GitHub Pages.

### Table of Contents

- Part A - [Syncing 'Create-React-App <App Name>' with GitHub Repository](#part-one)
- Part B - [Publishing 'Create-React-App <App Name>' onto GitHub Pages](#part-two)

### Part A - <a name="part-one"></a>Syncing 'Create-React-App <App Name>' with GitHub Repository

- Step 1: From your Create-React-App root folder initialize git via the `git init` command.

- Step 2: Whether you're working from a freshly created Create-React-App folder or touching up on the final details, it's always a good idea to `git add <file(s)>` and `git commit -m <message in quotes>` to commit your app's current state.

- Step 3: Visit github.com, log into your GitHub account if you haven't already, and hit `+` > `New repository` in the upper right corner. Enter the name of your app folder under `Repository Name`. DO NOT _Initialize this repository with a README_. Instead `Create repository`.

- Step 4: On the newly loaded page, copy the `git remote add origin git@github.com:<username>/<repo>.git` script and paste it in your terminal. Hit enter, then `git push -u origin master` to push up current files into your GitHub repo.

- Step 5: If you’re still working, please do so and commit often. If you’re done with the assignment. Proceed to Part B.

### Part B - <a name="part-two"></a>Publishing 'Create-React-App <App Name>' onto GitHub Pages

- Step 1: From Visual Studio Code Explorer (the left hand side file navigation tool that expands when clicking the dual pages icon), locate your package.json in your root folder and double-click to open. We’re going to make some edits.

- Step 3: Somewhere in the package.json, you will need to enter the following line.

  ```"homepage": "https://<username>.github.io/<repo-name>",```

Example:

```
  ...
    "private": true,
    "homepage": "https://julienshim.github.io/clicky-game",
    "dependencies": {
  ...

  Note: I personally put homepage between `private` and `dependencies` as shown above. 
        Wherever you put it, make sure you're mindful of the commas.
```

- Step 4: Back in your terminal, enter the following command: `yarn add gh-pages` (since we've been using yarn), but alternatively, you can use `npm install --save gh-pages`.

- Step 5. Back to your package.json, make sure you have the following marked in *bold* under `“scripts”` after `"deploy": "gh-pages -d build"`:

```
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
  **"start": "react-scripts start",
  "build": "react-scripts build",
  "test": "react-scripts test --env=jsdom",
  "eject": "react-scripts eject"**
}
```

- Step 6: Enter the following in your terminal: `npm run deploy`

- Step 7: Head back to your repo. Click `Settings` and under `GitHub Pages` confirm that your React App is published.

- Step 8: Might as well submit your links to bootcampspot. (edited)
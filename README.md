# Electron React App Set Up

## How to Setup an electron app to use react js for development

   1. Create a reactjs app app as usual using reactjs cli
   2. Add Electron **as a dev dependecy**
   3. Add Electron-builder { *allows us to bundle the app together for production* } **as a dev dependecy**
   4. add concurrently {{*allows us to run two processes together one after another*}} **as a dev dependecy**
   5. add wait-on {{*allows us to run scripts only after another process has completed*}} **as a dev dependecy**
   6. add cross-env and electron-is-dev {{**dependencies**}}
   
   7. Create the main js file in the publice Directory
   8. Update pacake.json replace ```private : true with main: "public/*filename.js*```
   9. **win.loadURL('index.html')** here u run a check to see if in dev mode or production
          1. if in dev load : ***http://localhost:3000*** 
          2. if in prod' load : ***`file://${path.join(__dirname,"../build/index.html")}***
  10. **update scripts**
           1. ***Scripts": {
           2. ***"react_start": "react-scripts start",
           3. ***"react_build": "react-scripts build",
           4. ***"react_test": "react-scripts test",
           5. ***"react_eject": "react-scripts eject",
           6. ***"electron_build":"electron-builder",
           7. ***"build":"npm run react-build && npm run electron_build",
           8. ***"start": "concurrently \"cross-env BROWSER=none npm run react_start\" \"wait-on http://localhost:3000 && electron .\""
           9. ***}, 
           
11. ***run ```npm start``` ***

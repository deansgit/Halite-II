### Offline Visualiser

Download the Halite-II master directory zip file at https://github.com/HaliteChallenge/Halite-II.
Extract all files to a location you can easily access.

Install node.js at https://nodejs.org/en/ (6.11.5 LTS).

Install Ruby at https://www.ruby-lang.org/en/downloads/.
    Install all "optional" packages (MSYS2 options 1, 2, and 3)
    
Now that you have Ruby, add the gems bundler and jekyll:
>    ```
>    gem install bundler jekyll
>    ```
    
Install any extraneous dependencies that show up in the error messages (tzinfo, nogokiri, etc):
>    ```
>    gem install [NAMEOFPACKAGE]
>    ```

Update bundler (you may have to run this if step 4 doesn't work):
>    ```
>    bundle update    
>    ```

Now build the electron app. cd is a command to change directory.

Open the Halite-II folder you created in the first step.
Shift+right-click and select "Open command window here" (or Powershell on Win 10)
Enter the commands you see below to create the necessary files for the standalone visualizer.

#### Building the electron app

1. Install node packages for the website
    ```
    cd ../../website
    npm install
    ```

2. Install node packages for libhaliteviz
    ```
    cd ../libhaliteviz
    npm install
    ```

3. Install node packages for visualizer
    ```
    cd ../tools/standalone_visualizer
    npm install
    ```

4. Build the CSS

    ```
    cd ../../website
    bundle exec jekyll build
    ```

5. Build the visualizer assets
   ```
   cd ../tools/standalone_visualizer
   npm run build
   ```

6. Start the app
    ```
    npm run start
    ```

#### Packaging

```
yarn electron-builder .
```

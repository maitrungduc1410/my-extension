# my-extension

> This is my project to create Chrome extension using VueJS. 

If you want to know how to build it see my [blog](https://viblo.asia/p/viet-chrome-extension-bang-vuejs-Ljy5VoVjKra) (Vietnamese, sorry if it's not your native languague)
## Build Setup (for extension)
To test the extension first you need to run this command to build project:
```bash
# install dependencies
npm install
# build project
npm run build
```
Then you should open List Chrome Extension in your browser, then you drag and drop folder `dist` into the browser.
Now your extension is available on your browser, play around with it :)

- If you want to change code go to folder `src`
## Build Setup (for running as web app)
Beside running as a extension the project is absolutely run like usual web app
``` bash
# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```

For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).

# my-first-vue-app

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).

### Deploy Azure
- package.json file add start command, that executes Azure after deploy.
"start": "vue-cli-service serve"

- modify vue.config.js, to allow production web server url
devServer: {
    allowedHosts: "all",
  }

- Stop and start Azure Application Service to load the new configuration
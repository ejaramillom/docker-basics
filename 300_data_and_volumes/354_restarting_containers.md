# code changes

- to reload code changes in node js (or other runtime environments) we have to reload our container to see changes in the codebase (for example a log)
- `console.log('Test')` we added this to the code but it does not show when writing `docker logs feedback-app`, then we have to `docker stop` and `docker start`
- to avoid this, we add in the package.json the following

```
"scripts": {
  "start": "nodemon start.js"
},
"devDependencies": {
  "nodemon": "2.0.4"
}
```

and in the docker file

`CMD ["npm", "start"]`

so that the container starts with the dependency


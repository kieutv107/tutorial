# How to deploy Flask with Reactjs on IIS subfolder

## Setup on Reactjs

1. Add `homepage` in file `package.json`
```json
"homepage": "https://domain.com/subfolder",
```

2. Set props `basename` for ReactRouter
```jsx
<Router basename={process.env.PUBLIC_URL}>
  <Route path='/' component={Home} />
  {/* … */}
</Router>
```

3. Change all api urls use prefix `process.env.PUBLIC_URL`
```js
axios.post(`${process.env.PUBLIC_URL}/api/user/login`, {code: code})
```

## Set up on Flask

1. Define `URL_PREFIX` in `config.py`
```py
URL_PREFIX='/subfolder'
```
2. Append url_prefix= at any Blueprints
3. Add static_folder for main views

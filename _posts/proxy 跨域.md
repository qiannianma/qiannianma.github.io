###### proxy 跨域

Proxy Setting

http://proxy.wdf.sap.corp  8080
localhost;127.0.0.1;*.local;*.sap.corp;10.*;*.corp.sap;*.co.sap.com;*.sap.biz

proxy
https://sapui5.hana.ondemand.com/#/topic/5bb388fc289d44dca886c8fa25da466e.html#loio5bb388fc289d44dca886c8fa25da466e__CORSAnywhere

跨域：npm install proxy----->创建proxy.js
https://www.npmjs.com/package/proxy

```js
var cors_proxy = require('cors-anywhere');
// Listen on a specific IP Address
var host = 'localhost';

// Listen on a specific port, adjust if necessary
var port = 8081;

cors_proxy.createServer({
originWhitelist: [], // Allow all origins
requireHeader: ['origin', 'x-requested-with'],
removeHeaders: ['cookie', 'cookie2']
})
.listen(port, host, function() {
console.log('Running CORS Anywhere on ' + host + ':' + port);
});
```

package.json
```json
"scripts": {
"start": "ui5 serve --port 8083",
"serve": "ui5 serve",
"proxy": "node proxy.js",
```

npm run proxy/proxy.js
# Dev Tools

## Debugging

There are many tools you can use to debug you app, but simply using Chrome DevTools usually works great.

Other tools to look at:

 - [react-devtools](https://github.com/facebook/react-devtools/tree/master/packages/react-devtools)
 - [react-native-debugger](https://github.com/jhen0409/react-native-debugger)
 - [reactotron](https://github.com/infinitered/reactotron)

## Network Requests

Development mode proxies all network requests to the open devtools network panel.

Get a [CORS extension](https://chrome.google.com/webstore/search/cors?hl=en) for Chrome to allow requests to fetch restricted requests and enable for the devtools page.

If you are having problems with this feature, you can bypass network requests with the following:

```js
import xhr from 'utils/xhr';

xhr.bypass(() => fetch('https://google.com'))
.then(data => data.json());

const ws = new WebSocket('ws://google.com');
xhr.bypass(() => ws.open());

// Also supported
xhr.toggle();
xhr.enabled();
xhr.disabled();
```

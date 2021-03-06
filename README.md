# qishi-fetch

![es6-promise](https://img.shields.io/badge/es6--promise-4.2.5-brightgreen.svg)
![whatwg-fetch](https://img.shields.io/badge/whatwg--fetch-3.0.0-orange.svg)

Fetch for browser.

## Install

```bash
$ npm isntall qishi-fetch
```

## Including qishi-fetch

### Script tag

```html
<script src="/node_modules/reco-fetch/dist/recoFetch.min.js"></script>
```

### Import

```javscript
import qishiFetch from 'qishi-fetch'
```

## Config

In addition to the parameters given below, please combine other parameters [MDN](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch#Supplying_request_options).

```javascript
/**
 * @param {String, must} url    API URL
 * @param {String, must} options Parameter objects, including:
 *        method  {String, optional} Request method, default 'get'
 *        headers {Object, optional} Set request header
 *        params  {Object, optional} url parameters
 *        body    {Object, optional} request body
 *        timeout {Number, optional} Request timeout
 *        type    {String, optional} When 'post' requests, you can set: 'json', 'formData'
 */

const options = {
  method: 'post',
  headers: {},
  timeout: 1000,
  body: {
    id: 1,
    value: 2
  }
}

recoFetch(url, options). then(res => {
  console.log(res)
}).catch(err => {
  console.log(err)
})
```

## Example

### GET

```javascript
const options = {
  method: 'get',
  params: {
    key: 1,
    value: 2
  }
}

recoFetch(url, options). then(res => {
  console.log(res)
}).catch(err => {
  console.log(err)
})
```

### POST JSON

```javascript
const options = {
  method: 'post',
  body: {
    key: 1,
    value: 2
  },
  type: 'json'
}

recoFetch(url, options). then(res => {
  console.log(res)
}).catch(err => {
  console.log(err)
})
```

**POST formData**

```javascript
const options = {
  method: 'post',
  body: {
    key: 1,
    value: 2
  },
  type: 'formData'
}

// or

const form = document.querySelector('form')
const options = {
  method: 'post',
  body: form
}

recoFetch(url, options). then(res => {
  console.log(res)
}).catch(err => {
  console.log(err)
})
```

### PUT

```javascript
const options = {
  method: 'put',
  body: {
    key: 1,
    value: 2
  },
  type: 'json'
}

// or

const options = {
  method: 'put',
  body: JSON.stringify({
    key: 1,
    value: 2
  })
}

recoFetch(url, options). then(res => {
  console.log(res)
}).catch(err => {
  console.log(err)
})
```

### DELETE

```javascript
const options = {
  method: 'delete',
  params: {
    key: 1,
    value: 2
  }
}

recoFetch(url, options). then(res => {
  console.log(res)
}).catch(err => {
  console.log(err)
})
```

### uploadFile

```javascript
const fileField = document.querySelector("input[type='file']")

const options = {
  method: 'post',
  body: {
    file: fileField.files[0]
  },
  type: 'formData'
}

// or

const formData = new FormData()
const fileField = document.querySelector("input[type='file']")

formData.append('file', fileField.files[0])

const options = {
  method: 'post',
  body: formData
}

recoFetch(url, options). then(res => {
  console.log(res)
}).catch(err => {
  console.log(err)
})
```

## License
[MIT](https://github.com/recoluan/reco-fetch/blob/master/LICENSE)

# Sails.js API Data Provider For React-Admin

Sails.js API Data Provider for [react-admin](https://github.com/marmelab/react-admin). Based on [ra-data-json-server](https://github.com/marmelab/react-admin/tree/master/packages/ra-data-json-server).

## Installation

```sh
npm install --save mpampin/ra-data-json-sails
```

## REST Dialect

| REST verb            | API calls
|----------------------|----------------------------------------------------------------
| `GET_LIST`           | `GET http://my.api.url/posts?sort=title%20ASC&skip=0&limit=50&title=bar`
| `GET_ONE`            | `GET http://my.api.url/posts/123`
| `CREATE`             | `POST http://my.api.url/posts/123`
| `UPDATE`             | `PUT http://my.api.url/posts/123`
| `DELETE`             | `DELETE http://my.api.url/posts/123`
| `GET_MANY`           | `GET http://my.api.url/posts/123, GET http://my.api.url/posts/456, GET http://my.api.url/posts/789`
| `GET_MANY_REFERENCE` | `GET http://my.api.url/posts?author_id=345`

**Note**: The JSON Server REST Data Provider expects the API to include a `X-Total-Count` header in the response to `GET_LIST` calls. The value must be the total number of resources in the collection. This allows react-admin to know how many pages of resources there are in total, and build the pagination controls.

```
X-Total-Count: 319
```

If your API is on another domain as the JS code, you'll need to whitelist this header with an `Access-Control-Expose-Headers` [CORS](https://developer.mozilla.org/en-US/docs/Web/HTTP/Access_control_CORS) header.

```
Access-Control-Expose-Headers: X-Total-Count
```

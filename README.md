# Ubigeo
Provides data about regions, provincies and districts of the country Peru.

## Install
```sh
npm install --save ubigeo
yarn add ubigeo
```

## API
```
regions(): Returns all regions
find(keys): Filters regions by keys ({code: 'xxx'} or {name: 'xxxx'})
include(param): Includes in the data, 'provincies' or 'districts'
get(): Is neccesary to specify it the final for to return the result
```

## Usage
```js
const ubigeo = require('ubigeo')

let regions = ubigeo.regions().get()
let regions_provincies = ubigeo.regions().include('provincies').get()
let regions_districts = ubigeo.regions().include('districts').get()

let ucayali = ubigeo.regions().find({ name: 'ucayali' }).get()
let ucayali_provincies = ubigeo.regions().find({ name: 'ucayali' }).include('provincies').get()
let ucayali_districts = ubigeo.regions().find({ name: 'ucayali' }).include('districts').get()

console.log(ucayali_provincies)
/*
[
 {
  "code": "25",
  "name": "Ucayali",
  "provincies": [
   {
    "code": "01",
    "provincie": "Coronel Portillo"
   },
   {
    "code": "02",
    "provincie": "Atalaya"
   },
   {
    "code": "03",
    "provincie": "Padre Abad"
   },
   {
    "code": "04",
    "provincie": "Purús"
   }
  ]
 }
]
*/
```

## License
MIT

# Gehl / STAE

## Seattle, WA

#### API URLs

See [using the api](#using-the-api) for more info.

- [Air Measurement]()
- [Transit Station + Bike Share]()
- [Transit Route]()
- [311 Issue]()
- [Gehl Public Life Observation]()
- [Traffic Jam]()

#### CSV Dump

- [Air Measurement]()
- [Transit Station + Bike Share]()
- [Transit Route]()
- [311 Issue]()
- [Gehl Public Life Observation]()
- [Traffic Jam]()

#### JSON Dump

- [Air Measurement]()
- [Transit Station + Bike Share]()
- [Transit Route]()
- [311 Issue]()
- [Gehl Public Life Observation]()
- [Traffic Jam]()

#### GeoJSON Dump

- [Air Measurement]()
- [Transit Station + Bike Share]()
- [Transit Route]()
- [311 Issue]()
- [Gehl Public Life Observation]()
- [Traffic Jam]()

## Vancouver, BC 
## San Francisco, CA
##  All Locations

# Using the API

## Pagination

Use the `limit` and `offset` querystring parameters to page through the data.

Example, requesting page 3: `?limit=1000&offset=2000`

## Geospatial Search

Use the `within` querystring object to limit the results to a bounding box.

Example: `?within[xmin]=1&within[xmax]=2&within[ymin]=1&within[ymax]=2`

Example JS:

```js
import request from 'superagent'

request.get('https://municipal.systems/v1/url')
  .query({
    within: {
      xmin: 1,
      xmax: 2,
      ymin: 1,
      ymax: 2
    }
  })
```

## Filters

Use the `filters` querystring object to filter the results of your data in any arbitrary way.

Example JS:

```js
import request from 'superagent'

request.get('https://municipal.systems/v1/url')
  .query({
    filters: [
      {
        data: {
          receivedAt: {
            $lt: new Date('1/1/2017')
          }
        }
      }
    ]
  })
```

## Orderings

Use the `orderings` querystring object to order the results of your data in any arbitrary way.

Example JS:

```js
import request from 'superagent'

request.get('https://municipal.systems/v1/url')
  .query({
    orderings: [
      {
        field: 'data.receivedAt',
        direction: 'desc'
      }
    ]
  })
```

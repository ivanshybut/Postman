# Create method __get__, __post__, __put__, __delete__

## Base URL:  https://rahulshettyacademy.com 
## key =qaclick123
- 🔶POST:
1. ➡️ Resource: /maps/api/place/add/json
2. ➡️ Sample Body:

```json
{
  "location": {
    "lat": -38.383494,
    "lng": 33.427362
  },
  "accuracy": 50,
  "name": "Frontline house",
  "phone_number": "(+91) 983 893 3937",
  "address": "29, side layout, cohen 09",
  "types": [
    "shoe park",
    "shop"
  ],
  "website": "http://google.com",
  "language": "French-IN"
}

```

- 🔶GET:
1. Resource: /maps/api/place/get/json
2. Query Parameters: 

```json
key,  place_id ( place_id  value comes from Add place response)
```
- 🔶PUT:
1. Resource: /maps/api/place/update/json
2. Sample Body:

```json
{
  "place_id":"8d2573bdf6ceec0e474c5f388fa917fb",
  "address":"70 Summer walk, USA",
  "key":"qaclick123"
}
```
- 🔶DELETE:
1.  Resource: /maps/api/place/delete/json
2.  Sample Body:

```json
{
    "place_id":"928b51f64aed18713b0d164d9be8d67f"
}
```

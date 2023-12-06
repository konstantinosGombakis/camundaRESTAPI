For the future to add -H 'NGSILD-Tenant: ed-tenant'

## Send data for the urn:ngsi-ld:ed:TemperatureSensor1

```console
curl -iL -X POST  'http://localhost:1026/ngsi-ld/v1/entityOperations/upsert' \
-H 'Content-Type: application/ld+json' \
-H 'Accept: application/json' \
-d '
[
  {
    "id": "urn:ngsi-ld:ed:TemperatureSensor1",
    "type": "TemperatureSensor",
    "@context": [
      "https://raw.githubusercontent.com/konstantinosGombakis/FORTESIE_data_model/main/demo/fortesie-context.jsonld"
    ],
  
    "temparature": {
      "type": "Property",
      "value": 10,
      "unitCode": "CEL",
      "observedAt": "2023-09-16T17:06:49Z"
    }
  }
  ]
'
```

## Get data of a specific entity/sensor

Reading add the data from the entity/sensors TemperatureSensor1

```console
curl -G -s -iX GET 'http://localhost:1026/ngsi-ld/v1/entities/urn:ngsi-ld:ed:TemperatureSensor1' \
-H 'Link: <https://raw.githubusercontent.com/konstantinosGombakis/FORTESIE_data_model/main/demo/fortesie-context.jsonld>; rel="http://www.w3.org/ns/json-ld#context"; type="application/ld+json"' \
-d 'options=sysAttrs'
```



## Send data for the urn:ngsi-ld:ed:ieq1

```console
curl -iL -X POST  'http://localhost:1026/ngsi-ld/v1/entityOperations/upsert' \
-H 'Content-Type: application/ld+json' \
-H 'Accept: application/json' \
-d '
[
  {
    "id": "urn:ngsi-ld:ed:ieq1",
    "type": "IEQSensor",
    "@context": [
      "https://raw.githubusercontent.com/konstantinosGombakis/FORTESIE_data_model/main/demo/fortesie-context.jsonld"
    ],
    "temparature": {
      "type": "Property",
      "value": 10,
      "unitCode": "CEL",
      "observedAt": "2023-09-16T17:06:49Z"
    },
        "relativeHumidity": {
      "type": "Property",
      "value": 39.0,
      "unitCode": "P1",
      "observedAt": "2023-09-15T16:04:49Z"
    }
  }
  ]
'
```

## Get data of a specific entity/sensor

Reading add the data from the entity/sensors TemperatureSensor1

```console
curl -G -s -iX GET 'http://localhost:1026/ngsi-ld/v1/entities/urn:ngsi-ld:ed:ieq1' \
-H 'Link: <https://raw.githubusercontent.com/konstantinosGombakis/FORTESIE_data_model/main/demo/fortesie-context.jsonld>; rel="http://www.w3.org/ns/json-ld#context"; type="application/ld+json"' \
-d 'options=sysAttrs'
```
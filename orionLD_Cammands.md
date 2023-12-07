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
      "http://ed-ld-context/ed-context.jsonld"
    ],
  
    "temperature": {
      "type": "Property",
      "value": 10,
      "unitCode": "CEL",
      "observedAt": "2023-09-16T17:06:49Z"
    }
  }
  ]
'
```

## Get data of TemperatureSensor1

Reading add the data from the entity/sensors TemperatureSensor1

```console
curl -X GET 'http://localhost:1026/ngsi-ld/v1/entities/urn:ngsi-ld:ed:TemperatureSensor1' \
-H 'Link: <http://ed-ld-context/ed-context.jsonld>'

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
      "http://ed-ld-context/ed-context.jsonld"
    ],
    "temperature": {
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

## Reading data from the entity/sensors ieq1


```console
curl -X GET 'http://localhost:1026/ngsi-ld/v1/entities/urn:ngsi-ld:ed:ieq1' \
-H 'Link: <http://ed-ld-context/ed-context.jsonld>'
```


## Set temperature, urn:ngsi-ld:ed:TemperatureSensor1 at 1000oC
curl -iL -X POST  'http://localhost:1026/ngsi-ld/v1/entityOperations/upsert' \
-H 'Content-Type: application/ld+json' \
-H 'Accept: application/json' \
-d '
[
  {
    "id": "urn:ngsi-ld:ed:TemperatureSensor1",
    "type": "TemperatureSensor",
    "@context": [
      "http://ed-ld-context/ed-context.jsonld"
    ],
  
    "temperature": {
      "type": "Property",
      "value": 50,
      "unitCode": "CEL",
      "observedAt": "2023-09-16T17:10:49Z"
    }
  }
  ]
'

## Set temperature, urn:ngsi-ld:ed:TemperatureSensor1 at 50oC
curl -iL -X POST  'http://localhost:1026/ngsi-ld/v1/entityOperations/upsert' \
-H 'Content-Type: application/ld+json' \
-H 'Accept: application/json' \
-d '
[
  {
    "id": "urn:ngsi-ld:ed:TemperatureSensor1",
    "type": "TemperatureSensor",
    "@context": [
      "http://ed-ld-context/ed-context.jsonld"
    ],
  
    "temperature": {
      "type": "Property",
      "value": 50,
      "unitCode": "CEL",
      "observedAt": "2023-09-16T17:10:49Z"
    }
  }
  ]
'
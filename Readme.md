## Run example

1. Run docker with all images: ```docker compose up -d```
2. Load sensor data to Orion-LD
    - See [orionLD_Cammands.md](./orionLD_Cammands.md)  OR
    - [Postman collection](./camundaRest.postman_collection.json)
3. Open any bpmb (getData, getDataAllInOne, getDataMultipleAllInOne), deploy and run it. **IMPORTANT** On the Service task, Connector input. url you need to specify the endpoint to access the data ie http://ed-orion-ld:1026/ngsi-ld/v1/entities/urn:ngsi-ld:ed:ieq1 . On our example the Orion-LD is running on the ed-orion-ld:1026, see [docker-compose.yml](./docker-compose.yml) -> container_name
4. Open the log file of the camunda container to see the output. For "getData.bpmn" it should be like
```console
____________________________________
Keys: [id, temperature, type]
Values: [urn:ngsi-ld:ed:TemperatureSensor1, [observedAt:2023-09-16T17:06:49.000Z, type:Property, unitCode:CEL, value:10], TemperatureSensor]
Value for 'temperature': 10
____________________________________
Values TemperatureSensor1: 10
```
5. See camunda_rest.gif 


## Example simpleIf process

1. Set temperature of urn:ngsi-ld:ed:TemperatureSensor1 at 50oC with command from [orionLD_Cammands.md](./orionLD_Cammands.md) or postman
2. Run the "simpleIf.bpmn" and open the instance in Camunda Cockpit
3. Raise the temperature to 1000oC by running command from [orionLD_Cammands.md](./orionLD_Cammands.md) or postman 
4. The presses finish 
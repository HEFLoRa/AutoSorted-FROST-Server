Wichtig zu wissen: local läuft der FROST-Server immer unter http://meinhost:<MEINPORT>/FROST-Server
Wenn man das ändern möchte muss der Dienst hinter einen ReversePoxy.
damit kannst auf der machine testen, ob der FROST erreichbar ist:  curl http://127.0.0.1:8080/FROST-Server/v1.1/

Du solltest dann sowas erhalten:

❯ curl http://127.0.0.1:8080/FROST-Server/v1.1/
{
  "value" : [ {
    "name" : "Datastreams",
    "url" : "https://gi3.gis.lrg.tum.de/frost/v1.1/Datastreams"
  }, {
    "name" : "MultiDatastreams",
    "url" : "https://gi3.gis.lrg.tum.de/frost/v1.1/MultiDatastreams"
  }, {
    "name" : "FeaturesOfInterest",
    "url" : "https://gi3.gis.lrg.tum.de/frost/v1.1/FeaturesOfInterest"
  }, {
    "name" : "HistoricalLocations",
    "url" : "https://gi3.gis.lrg.tum.de/frost/v1.1/HistoricalLocations"
  }, {
    "name" : "Locations",
    "url" : "https://gi3.gis.lrg.tum.de/frost/v1.1/Locations"
  }, {
    "name" : "Observations",
    "url" : "https://gi3.gis.lrg.tum.de/frost/v1.1/Observations"
  }, {
    "name" : "ObservedProperties",
    "url" : "https://gi3.gis.lrg.tum.de/frost/v1.1/ObservedProperties"
  }, {
    "name" : "Sensors",
    "url" : "https://gi3.gis.lrg.tum.de/frost/v1.1/Sensors"
  }, {
    "name" : "Things",
    "url" : "https://gi3.gis.lrg.tum.de/frost/v1.1/Things"
  } ],
  "serverSettings" : {
    "conformance" : [ "http://www.opengis.net/spec/iot_sensing/1.1/req/batch-request/batch-request", "http://www.opengis.net/spec/iot_sensing/1.1/req/create-observations-via-mqtt/observations-creation", "http://www.opengis.net/spec/iot_sensing/1.1/req/create-update-delete", "http://www.opengis.net/spec/iot_sensing/1.1/req/data-array/data-array", "http://www.opengis.net/spec/iot_sensing/1.1/req/datamodel", "http://www.opengis.net/spec/iot_sensing/1.1/req/multi-datastream", "http://www.opengis.net/spec/iot_sensing/1.1/req/receive-updates-via-mqtt/receive-updates", "http://www.opengis.net/spec/iot_sensing/1.1/req/request-data", "http://www.opengis.net/spec/iot_sensing/1.1/req/resource-path/resource-path-to-entities", "https://fraunhoferiosb.github.io/FROST-Server/extensions/GeoJSON-ResultFormat.md", "https://github.com/INSIDE-information-systems/SensorThingsAPI/blob/master/CSV-ResultFormat/CSV-ResultFormat.md" ],
    "http://www.opengis.net/spec/iot_sensing/1.1/req/create-observations-via-mqtt/observations-creation" : {
      "endpoints" : [ "mqtt://gi3.gis.lrg.tum.de:1883" ]
    },
    "http://www.opengis.net/spec/iot_sensing/1.1/req/receive-updates-via-mqtt/receive-updates" : {
      "endpoints" : [ "mqtt://gi3.gis.lrg.tum.de:1883" ]
    }
  }
}%       

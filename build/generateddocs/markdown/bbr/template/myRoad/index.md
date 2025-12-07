
# My Road (Schema)

`ogc.bbr.template.myRoad` *v0.1*

An example road schema

[*Status*](http://www.opengis.net/def/status): Under development

## Examples

### Sample reoad
#### json
```json
{
  "type": "Feature",
  "geometry": {
    "type": "LineString",
    "coordinates": [
      [-3.70379, 40.41678],
      [-3.70250, 40.41740]
    ]
  },
  "properties": {
    "highway": "motorway",
    "name": "A-7 Autovía del Mediterráneo",
    "surface": "asphalt",
    "oneway": "yes",
    "lanes": 3,
    "maxspeed": "120",
    "bridge": "no",
    "tunnel": "no",
    "source": "survey 2024-09",
    "underMaintenance": false
  }
}
```

#### jsonld
```jsonld
{
  "@context": "https://avillar.github.io/bblocks-idays-example/build/annotated/bbr/template/myRoad/context.jsonld",
  "type": "Feature",
  "geometry": {
    "type": "LineString",
    "coordinates": [
      [
        -3.70379,
        40.41678
      ],
      [
        -3.7025,
        40.4174
      ]
    ]
  },
  "properties": {
    "highway": "motorway",
    "name": "A-7 Autov\u00eda del Mediterr\u00e1neo",
    "surface": "asphalt",
    "oneway": "yes",
    "lanes": 3,
    "maxspeed": "120",
    "bridge": "no",
    "tunnel": "no",
    "source": "survey 2024-09",
    "underMaintenance": false
  }
}
```

#### ttl
```ttl


```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: My example schema
type: object
allOf:
- $ref: https://ogcincubator.github.io/bblocks-overturemaps/build/annotated/overturemaps/schemas/transportation/segment/schema.yaml
- $ref: https://ogcincubator.github.io/bblocks-osm/build/annotated/osm/features/highway/schema.yaml
properties:
  properties:
    properties:
      pavementConditionIndex:
        type: number
        minimum: 0
        maximum: 100
        x-jsonld-id: https://example.com/my/namespace/pavementConditionIndex
      maintenanceZone:
        type: string
        x-jsonld-id: https://example.com/my/namespace/maintenanceZone
        x-jsonld-type: '@id'
        x-jsonld-base: https://example.com/my/namespace/maintenanceZones/
      underMaintenance:
        type: boolean
        x-jsonld-id: https://example.com/my/namespace/isUnderMaintenance
x-jsonld-prefixes:
  myNamespace: https://example.com/my/namespace/

```

Links to the schema:

* YAML version: [schema.yaml](https://avillar.github.io/bblocks-idays-example/build/annotated/bbr/template/myRoad/schema.json)
* JSON version: [schema.json](https://avillar.github.io/bblocks-idays-example/build/annotated/bbr/template/myRoad/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "id": {},
    "geometry": {
      "@context": {
        "coordinates": {},
        "bbox": {}
      }
    },
    "subclass_rules": {
      "@context": {
        "between": {},
        "value": {}
      }
    },
    "access_restrictions": {
      "@context": {
        "between": {},
        "access_type": {},
        "when": {
          "@context": {
            "during": {},
            "heading": {},
            "using": {},
            "recognized": {},
            "mode": {},
            "vehicle": {
              "@context": {
                "dimension": {},
                "comparison": {},
                "value": "rdf:value",
                "unit": "http://qudt.org/vocab/unit/"
              }
            }
          }
        }
      }
    },
    "level": "om:hasLevel",
    "level_rules": {
      "@context": {
        "between": {},
        "value": {}
      }
    },
    "theme": {},
    "type": {},
    "version": {},
    "sources": {
      "@context": {
        "between": {},
        "property": {},
        "dataset": {},
        "license": {},
        "record_id": {},
        "update_time": {},
        "confidence": {}
      }
    },
    "names": {
      "@context": {
        "primary": {},
        "common": {},
        "rules": {
          "@context": {
            "between": {},
            "side": {},
            "variant": {},
            "language": {},
            "perspectives": {
              "@context": {
                "mode": {},
                "countries": {}
              }
            },
            "value": {}
          }
        }
      }
    },
    "subtype": {},
    "class": {},
    "destinations": {
      "@context": {
        "labels": {
          "@context": {
            "value": {}
          }
        },
        "symbols": {},
        "from_connector_id": {},
        "to_segment_id": {},
        "to_connector_id": {},
        "when": {
          "@context": {
            "heading": {}
          }
        },
        "final_heading": {}
      }
    },
    "prohibited_transitions": {
      "@context": {
        "between": {},
        "sequence": {
          "@context": {
            "connector_id": {},
            "segment_id": {}
          }
        },
        "final_heading": {},
        "when": {
          "@context": {
            "heading": {},
            "during": {},
            "using": {},
            "recognized": {},
            "mode": {},
            "vehicle": {
              "@context": {
                "dimension": {},
                "comparison": {},
                "value": "rdf:value",
                "unit": "http://qudt.org/vocab/unit/"
              }
            }
          }
        }
      }
    },
    "road_surface": {
      "@context": {
        "@base": "https://w3id.org/ogc/om/surfaces/",
        "between": {},
        "value": "@id"
      },
      "@id": "osm:hasSurfaceType"
    },
    "road_flags": {
      "@context": {
        "between": {},
        "values": {}
      }
    },
    "speed_limits": {
      "@context": {
        "between": {},
        "min_speed": {
          "@context": {
            "value": "rdf:value",
            "unit": "qudt:hasUnit"
          },
          "@id": "om:hasMinSpeed"
        },
        "max_speed": {
          "@context": {
            "value": "rdf:value",
            "unit": "qudt:hasUnit"
          },
          "@id": "om:hasMaxSpeed"
        },
        "is_max_speed_variable": "om:isMaxSpeedVariable",
        "when": {
          "@context": {
            "during": {},
            "heading": {},
            "using": {},
            "recognized": {},
            "mode": {},
            "vehicle": {
              "@context": {
                "dimension": {},
                "comparison": {},
                "value": "rdf:value",
                "unit": "http://qudt.org/vocab/unit/"
              }
            }
          },
          "@id": "om:when",
          "@type": "@json"
        }
      },
      "@id": "om:hasSpeedLimit"
    },
    "width_rules": {
      "@context": {
        "between": {},
        "value": {}
      }
    },
    "subclass": {},
    "rail_flags": {
      "@context": {
        "between": {},
        "values": {}
      }
    },
    "connectors": {
      "@context": {
        "connector_id": {},
        "at": {}
      }
    },
    "routes": {
      "@context": {
        "between": {},
        "network": {},
        "ref": {},
        "symbol": {}
      }
    },
    "properties": {},
    "highway": {
      "@context": {
        "motorway": "osm:Motorway",
        "trunk": "osm:Trunk",
        "primary": "osm:Primary",
        "secondary": "osm:Secondary",
        "tertiary": "osm:Tertiary",
        "unclassified": "osm:Unclassified",
        "residential": "osm:Residential",
        "service": "osm:Service",
        "motorwayLink": "osm:MotorwayLink",
        "trunkLink": "osm:TrunkLink",
        "primaryLink": "osm:PrimaryLink",
        "secondaryLink": "osm:SecondaryLink",
        "tertiaryLink": "osm:TertiaryLink",
        "living_street": "osm:LivingStreet",
        "pedestrian": "osm:Pedestrian",
        "busway": "osm:Busway",
        "bus_guideway": "osm:BusGuideway",
        "bus_stop": "osm:BusStop",
        "bus_station": "osm:BusStation",
        "raceway": "osm:Raceway",
        "footway": "osm:Footway",
        "path": "osm:Path",
        "track": "osm:Track",
        "cycleway": "osm:Cycleway",
        "bridleway": "osm:Bridleway",
        "steps": "osm:Steps",
        "crossing": "osm:Crossing",
        "road": "osm:Road",
        "construction": "osm:Construction"
      },
      "@id": "@type",
      "@type": "@id"
    },
    "oneway": "osm:isOneWay",
    "surface": {
      "@context": {
        "@base": "https://example.com/osm/surfaces/"
      },
      "@id": "osm:hasSurfaceType",
      "@type": "@id"
    },
    "name": "rdfs:label",
    "lanes": "osm:hasLaneCount",
    "maxspeed": {},
    "bridge": {},
    "tunnel": {},
    "cycleway": {},
    "sidewalk": {},
    "access": {},
    "source": "dct:source",
    "pavementConditionIndex": "myNamespace:pavementConditionIndex",
    "maintenanceZone": {
      "@context": {
        "@base": "https://example.com/my/namespace/maintenanceZones/"
      },
      "@id": "myNamespace:maintenanceZone",
      "@type": "@id"
    },
    "underMaintenance": "myNamespace:isUnderMaintenance",
    "wikidata": {
      "@id": "rdfs:seeAlso",
      "@type": "@id",
      "@context": {
        "@base": "https://www.wikidata.org/wiki/"
      }
    },
    "address": {
      "@id": "vcard:hasAddress",
      "@type": "@id",
      "@context": {
        "freeform": "rdf:value",
        "locality": "vcard:hasLocality",
        "postCode": "vcard:hasPostalCode",
        "region": "vcard:hasRegion",
        "countryName": "vcard:hasCountryName"
      }
    },
    "allNames": {
      "@id": "@nest",
      "@context": {
        "primary": "skos:prefLabel",
        "common": {
          "@id": "skos:altLabel",
          "@container": "@language"
        }
      }
    },
    "om": "https://w3id.org/ogc/om/",
    "vcard": "http://www.w3.org/2006/vcard/ns#",
    "rdf": "http://www.w3.org/1999/02/22-rdf-syntax-ns#",
    "skos": "http://www.w3.org/2004/02/skos/core#",
    "qudt": "http://qudt.org/schema/qudt/",
    "myNamespace": "https://example.com/my/namespace/",
    "rdfs": "http://www.w3.org/2000/01/rdf-schema#",
    "osm": "https://example.com/osm/",
    "dct": "http://purl.org/dc/terms/",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://avillar.github.io/bblocks-idays-example/build/annotated/bbr/template/myRoad/context.jsonld)


# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/avillar/bblocks-idays-example](https://github.com/avillar/bblocks-idays-example)
* Path: `_sources/myRoad`


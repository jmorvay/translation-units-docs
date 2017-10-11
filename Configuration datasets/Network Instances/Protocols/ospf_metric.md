# OSPF metric configuration

## URL

```
openconfig-network-instance:network-instances/network-instance/<ni-name>/protocols/protocol/openconfig-policy-types:OSPF/<process-name>
```

## OPENCONFIG YANG

```json
{
    "protocol": [
        {
            "name": <process-name>,
            "identifier": "openconfig-policy-types:OSPF",
            "config": {
                "name": <process-name>,
                "identifier": "openconfig-policy-types:OSPF"
            }
            "ospfv2": {
                "global": {
                    "max-metric": {
                        "config": {
                            "set":true
                            "include": [ { "MAX_METRIC_INCLUDE_STUB" } ]
                        }
                    }
                }
                "areas": {
                    "area": [
                        {
                            "identifier": <area-id>,
                            "config": {
                                "identifier": <area-id>
                            },
                            "lsdb": {
                                "lsa-types": [
                                    {
                                         "lsa-type": {
                                             "type":"ROUTER_LSA"
                                         }
                                         "lsa-type": {
                                             "type":"SUMMARY_ASBR_LSA"
                                         }
                                         "lsa-type": {
                                             "type":"AS_EXTERNAL_LSA"
                                         }
                                    }
                                ]
                            }
                        }
                    ]
                }
            }
        }
    ]
}

TODO: lsdb parameters are not configurable @see https://github.com/openconfig/public/blob/master/release/models/ospf/openconfig-ospfv2-lsdb.yang
TODO: commands are not related to area (configure for all areas?)

```

## OS Configuration Commands

#### Cisco IOS XR 5.4.3

---
<pre>
router ospf &lt;process-name&gt;
  max-metric router-lsa include-stub summary-lsa external-lsa
</pre>
---

#### Junos

---
<pre>
set protocols ospf overload timeout 1200
</pre>
---
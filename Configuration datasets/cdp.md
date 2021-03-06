# Configure CDP interfaces

## URL

```
frinx-cdp:cdp
```

## OPENCONFIG YANG

[YANG models](https://github.com/FRINXio/openconfig/tree/master/cdp/src/main/yang)

```javascript
{
    "cdp": {
        "interfaces": {
            "interface": [
                {
                    "name": "<intf-id>",
                    "config": {
                        "name": "<intf-id>",
                        "enabled": true
                }
            ]
        }
    }
}
```


## OS Commands

### Cisco IOS Classic (15.2(4)S5) / XE (15.3(3)S2)

#### CLI

<pre>
interface &lt;intf-id&gt;
 cdp enable | no cdp enable
</pre>

*cdp enable* is conversion of *"enabled": true*  
*no cdp enable* is conversion of *"enabled": false*

##### Unit

### Cisco IOS XR (XRv 5.1.3 and XRv 6.1.2 tested)

#### CLI

<pre>
interface &lt;intf-id&gt;
 cdp | no cdp
</pre>

*cdp* is conversion of *"enabled": true*  
*no cdp* is conversion of *"enabled": false*

##### Unit

### Brocade (V5.6.0fT163)

#### CLI

<pre>
interface &lt;intf-id&gt;
 cdp enable | no cdp enable
</pre>

*cdp enable* is conversion of *"enabled": true*  
*no cdp enable* is conversion of *"enabled": false*

##### Unit
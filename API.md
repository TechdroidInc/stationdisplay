# API

The API point can be changed from the default (https://api.stationdisplay.com/station/departure-arrival) under advanced settings in the configuration app. 

The Station display will make the following request generaly every 30 seconds unless an error occured.

Your server must provide SSL but the certificate can be self-signed. At this time the Station Display can only make https requests.

The following headers are sent by the Station Display:
```
Authorization: Device authentication for official API
Accept-Language: Currently configured language: de-CH, fr-CH, it-CH or en-US
Content-Type: always: "application/json"
X-Board-Version: Hardware version (fixed)
X-Firmware-Version: Current firmware version
X-Uptime: Uptime im miliseconds
```

The API needs to deliver the data in the followng JSON format:
```javascript
{
    "info": {
        "sn": "Station Name",
        "p": "Platform Number"
    },
    "alert": {
        "active": false,
        "msg": "Alert Message to display",
        "int": 10
    },
    "dep": [
        {
            "direction": "H",
            "line": "1",
            "destination": "Destination",
            "is_nf": false,
            "line_ref": "",
            "ttl": 3,
            "is_skipped": false,
            "is_late": false,
            "is_live": false,
            "colors": {
                "f": {
                    "r": 0,
                    "g": 0,
                    "b": 0
                },
                "b": {
                    "r": 138,
                    "g": 181,
                    "b": 31
                }
            }
        },
        {
            "direction": "R",
            "line": "3",
            "destination": "Destination 2",
            "is_nf": false,
            "line_ref": "",
            "ttl": 5,
            "is_skipped": false,
            "is_late": false,
            "is_live": false,
            "colors": {
                "f": {
                    "r": 0,
                    "g": 0,
                    "b": 0
                },
                "b": {
                    "r": 138,
                    "g": 181,
                    "b": 31
                }
            }
        }
    ]
}
```

```
"direction": direction code, R or H
"line": Line number
"destination": Destination label
"is_nf": Accessibility marker (Niederflureinstieg)
"line_ref": Line reference (not used by Station Display),
"ttl": (Time to departure in minutes),
"is_skipped": Station was skipped (for example due to bus malfunction)
"is_late": Vehicle is more than 3 minutes delayed
"is_live": Time was adjusted with live data (changes marker on station display TTL)
"colors": F is font color in RGB, B is background color in RGB
```

meteor-visit-tracker
===================

Meteor Visit Tracker - Log web app visits for homebrew analytics and conversion attribution

Track:
  * IP Address
  * Referer
  * User Agent Raw
  * User Agent Parsed
    * Browser
    * OS
    * Device
  * Geo IP
    * City
    * Region (State)
    * Geo Coords
    * Country
  * Traffic Source ( Requires additional configuration )
    * SID (Source ID) : Could be a unique ID that points to TrafficSources collection record for Google Display
    * CMP : Marketing Campaign
    * S1 - S5 (Custom Variables) : Could be used to identify a certain ad or other info to relale a visit back to something
    
Example Link if you want to track traffic source:
`http://yoursite.com/?sid=googd&cmp=2341234&s1=ad4342&s2=dopetracker`

Node Packages Used:
* [ua-parser](https://github.com/tobie/ua-parser)
* [node-geoip](https://github.com/bluesmoon/node-geoip)


Example Visit Record:
```
{ 
referer: undefined,
ipAddress: '76.167.148.250',
userAgent: { 
 raw: 'Mozilla/5.0 (Macintosh; Intel Mac OS X 10_9_0) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/33.0.1750.152 Safari/537.36',
 os: { 
  family: 'Mac OS X',
  major: '10',
  minor: '9',
  patch: '0',
  patchMinor: null 
 },
 device: { 
  family: 'Other' 
 },
 browser: {
  family: 'Chrome',
  major: 33,
  minor: 0,
  patch: 1750 
 }
},
trafficSource: {
 sid: 'googd'
 cmp: '2341234'
 s1: 'ad4342'
 s2: 'dopetracker'
}
geo: { 
 range: [ 1286050560, 1286051327 ],
 country: 'US',
 region: 'CA',
 city: 'La Jolla',
 ll: [ 32.8667, -117.2481 ] 
} 
}

```

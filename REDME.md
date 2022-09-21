SYNC Intent는 어시스턴트가 사용자가 연결한 기기를 알고자 할 때 발생한다. 
유저가 계정을 연결하면 Fulfillment로 전송된다. 


## Request 
`intent : action.devices.SYNC` req가 fulfillment로 전송된다. 

User의 정보는 OAuth Server에서 받은 access token으로 구별한다. 

```js
{
  "requestId": "6894439706274654512",
  "inputs": [
    {
      "intent": "action.devices.SYNC"
    }
  ]
}
```

## Response
Fulfillment에서는 requestId와 payload를 응답한다. 

payload에는 계정의 모든 기기 및 기기 기능이 포함된다. 

```js
{
  "requestId": "6894439706274654512",
  "payload": {
    "agentUserId": "user123",
    "devices": [
      {
        "id": "123",
        "type": "action.devices.types.LIGHT",
        "traits": [
          "action.devices.traits.ColorSetting",
          "action.devices.traits.Brightness",
          "action.devices.traits.OnOff"
        ],
        "name": {
          "name": "Simple light"
        },
        "willReportState": true,
        "attributes": {
          "colorTemperatureRange": {
            "temperatureMinK": 2000,
            "temperatureMaxK": 6500
          }
        },
        "deviceInfo": {
          "manufacturer": "smart-home-inc",
          "model": "hs1234",
          "hwVersion": "3.2",
          "swVersion": "11.4"
        }
      }
    ]
  }
}
```


# Tags 
#date/2022/09/16 

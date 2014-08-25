FORMAT: X-1A

# Table Tracker API

# Group Active Orders

# /api/v1/activeorders

## GET
Retrieve all active orders

+ Response 200 (application/json)

        {
          "status": 200,
          "count": "1",
          "items": [
            {
              "elapsedTime": 2124,
              "uuid": "f73e89fe-c32c-4595-9b8a-ad8dcf9791c6",`
              "created": "2014-08-25T06:57:45",
              "orderType": "ON_PREMISE",
              "paged": "No",
              "locationName": "",
              "state": "started",
              "stateStarted": "2014-08-25T06:57:45",
              "name": "66"
            }
          ]
        }

## POST
Create an active order

+ Request (application/json)

        { 
          "name":"66", 
          "locationName" : "22"
          "orderType":"ON_PREMISES"
        }

+ Response 200 (application/json)

        {
          "status": 200,
          "activeorder": {
            "uuid": "f73e89fe-c32c-4595-9b8a-ad8dcf9791c6",
            "created": "2014-08-25T06:57:45",
            "orderType": "ON_PREMISE",
            "locationName": "",
            "state": "started",
            "stateStarted": "2014-08-25T06:57:45",
            "name": "66"
          }
        }

# /api/v1/activeorders/{name}

## DELETE
Clears an active order by its name. 

+ Response 200

        {
          "status": 200,
          "activeorder": {
            "uuid": "54ed91e6-286b-4912-b44c-7a7a3001d715",
            "created": "2014-08-25T08:09:42",
            "orderType": "ON_PREMISE",
            "locationName": "",
            "state": "cleared",
            "stateStarted": "2014-08-25T08:09:50",
            "name": "66"
          }
        }

+ Response 404
        
        Returned when order is not active.

# Group Orders

## All orders in system [/api/v1/orders{?offset}&{limit}]

+ Parameters

    + offset (optional, number) ... The starting point of the list.
    + limit  (optional, number) ... The max number of orders to retrieve.

### Retrieve all orders [GET]
Retrieve a list of orders starting at `offset` and returning a maximum `limit` of orders.

+ Response 200 (application/json)

        {
          "status": 200,
          "count": "7",
          "items": [
            {
              "locationName": null,
              "orderLocated": null,
              "uuid": "9e1da5eb-59ea-4003-9c1c-15160879c88d",
              "orderCleared": "2014-08-21T10:00:41+00:00",
              "orderType": "ON_PREMISE",
              "orderStarted": "2014-08-21T10:00:36+00:00",
              "type": "ORDER_SUMMARY",
              "name": "66"
            },
            {
              "locationName": null,
              "orderLocated": null,
              "uuid": "5d968a9c-77ec-41fd-aae8-54ef025b0f0d",
              "orderCleared": "2014-08-21T10:00:47+00:00",
              "orderType": "ON_PREMISE",
              "orderStarted": "2014-08-21T10:00:43+00:00",
              "type": "ORDER_SUMMARY",
              "name": "87"
            },
            {
              "locationName": "10",
              "orderLocated": "2014-08-21T10:05:55+00:00",
              "uuid": "85717acb-a36c-4cd1-847c-f3675f70f2e1",
              "orderCleared": "2014-08-21T10:06:04+00:00",
              "orderType": "ON_PREMISE",
              "orderStarted": "2014-08-21T10:05:27+00:00",
              "type": "ORDER_SUMMARY",
              "name": "66"
            },
            {
              "locationName": null,
              "orderLocated": null,
              "uuid": "57d5ad34-9977-44dc-8406-c1ece92ff85c",
              "orderCleared": "2014-08-21T13:13:57+00:00",
              "orderType": "ON_PREMISE",
              "orderStarted": "2014-08-21T13:13:35+00:00",
              "type": "ORDER_SUMMARY",
              "name": "87"
            },
            {
              "locationName": null,
              "orderLocated": null,
              "uuid": "27db2828-aa6d-44ab-8015-ac5b142be4e7",
              "orderCleared": "2014-08-21T13:13:46+00:00",
              "orderType": "ON_PREMISE",
              "orderStarted": "2014-08-21T13:13:33+00:00",
              "type": "ORDER_SUMMARY",
              "name": "66"
            },
            {
              "locationName": null,
              "orderLocated": null,
              "uuid": "f73e89fe-c32c-4595-9b8a-ad8dcf9791c6",
              "orderCleared": "2014-08-25T07:57:56+00:00",
              "orderType": "ON_PREMISE",
              "orderStarted": "2014-08-25T06:57:45+00:00",
              "type": "ORDER_SUMMARY",
              "name": "66"
            },
            {
              "locationName": "10",
              "orderLocated": "2014-08-21T10:05:59+00:00",
              "uuid": "a677aae2-d064-47d8-9ee3-8232da559b38",
              "orderCleared": "2014-08-21T10:06:01+00:00",
              "orderType": "ON_PREMISE",
              "orderStarted": "2014-08-21T10:05:19+00:00",
              "type": "ORDER_SUMMARY",
              "name": "87"
            }
          ]
        }

 
# Group Statistics

# /api/v1/statistics/{?target_time=300}

+ Parameters
    + target_time (optional, number) ... The target delivery time for an order.

## GET
Return the order statistics for the current day. 

+ Response (application/json)
        {
          "status": 200,
          "averageSeconds": 1809.5,
          "ordersToday": 2.0,
          "targetTime": 109.0,
          "percentGoal": 50.0
        }
 

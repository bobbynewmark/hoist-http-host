#Group Events
All API's related to Events within Hoist.

#Event Stream [/events]
A streaming API to get all events as they fire


  + Model (application/json)

    + Body

        [{
          "eventId":"1"
          ...
        },
        {
          "eventId":"2"
          ...
        }]


## Retrieve Event Stream [GET]

Retrieves a stream of events

   + Parameters

     + filter-field (optional, 'eventName' or 'correlationId') ... the field to filter the stream by

     + filter-value (optional, string) ... the value to filter the stream by

   + Request
       + Headers
           "Content-Type": "application/json"
           "Authorization": Hoist {auth-key}
           "X-Hoist-Filter-By": {filter-field}
           "X-Hoist-Filter-Value": {filter-value}

   + Response 200
       [Event Stream][]

#Event [/event/{id}]

+ Model (application/json)

  + Body

    {
      "eventId":"{id}",
      "eventName":"eventName",
      "correlationId":"correaltionId"
    }

## Retrieve a single Event [GET]
  + Parameters

    + id (string) ... Id of the event to return

  + Response 200

    [Event][]


## Add an event [POST]

create a new event
  + Parameters

    + id (optional, string) ... the id of the event to create

  + Request

    + Headers

      Content-Type: "application/json"
      Authorization: Hoist {auth-key}

    + Body
      ```
      {
        "eventName":"{eventName}"
      }
      ```

  + Response 201

    [Event][]
{
    "type" : "record",
    "name" : "channelEntity",
    "namespace" : "ie.aib.channels.avro.model",
    "fields" : [
        {
            "name": "header",
            "type": {
              "type": "record", "name": "Header", "fields":
              [
                {"name": "timestamp", "type": "long", "doc": "The system timestamp when the event was produced. Not overridable "},
                {"name": "eventType", "type": "string", "doc": "The verb describing the action that was performed in past tense. While the subject field accurately describes the entity the action was performed upon, additional identifiying data ensuring higher granularity may be present in the event type. These should be linked using kebab case. (i.e. a payment may be created in a number of ways so while subject identifierType may be payment and the identifierId may point to the particular payment - the event type could be domesticPayment-initiated. note that in this example the camel case is merely the name of the service. Other examples: validatePayments-PPGName-approved , credit-application-started)"},
                {"name": "application", "type": "string", "doc": "The source system that emitted the event. This should be in line with the TOKEN_CLIENT issued by the JWT signer service. (i.e. BPM, MAS) "},
                {"name": "correlationId","type": "string", "doc": "This field is correlation ID to link the Journey Event to other messages in the Journey topic and in other topics related to this Action (i.e. 93295c45-94fe-4b33-81e8-be06a32854a6) Default GUID"}
              ]
            },
            "doc": "AIB Enterprise Channel header"
          },
        { "name" : "analyticsID",  "type" : "string",  "default" : "NONE",  "doc" : "Analytics ID" },
        { "name" : "cifKey",  "type" : "string",  "default" : "NONE",  "doc" : "" },
        { "name" : "sessionID",  "type" : "string",  "default" : "NONE",  "doc" : "browser session" },
        { "name" : "channel",  "type" : "string",  "default" : "NONE",  "doc" : "Channel event was triggered from." },
        { "name" : "latitude",  "type" : "string",  "default" : "NONE",  "doc" : "Latitude of Device" },
        { "name" : "longitude",  "type" : "string",  "default" : "NONE",  "doc" : "Longitude of Device" },
        { "name" : "ipAddress",  "type" : "string",  "default" : "NONE",  "doc" : "IP Address of Device" },
        { "name" : "userAgent",  "type" : "string",  "default" : "NONE",  "doc" : "User agent string of device" },
        { "name" : "staffID",  "type" : "string",  "default" : "NONE",  "doc" : "Staff ID who triggered the event." },
        { "name" : "region",  "type" : "string",  "default" : "NONE",  "doc" : "Region" },
        { "name" : "appVersion",  "type" : "string",  "default" : "NONE",  "doc" : "Version of the Mobile App" },
        { "name" : "timezone",  "type" : "string",  "default" : "NONE",  "doc" : "Timezone of the device" },
        { "name" : "cardType",  "type" : "string",  "default" : "NONE",  "doc" : "Card type e.g. Credit, Debit" },
        { "name" : "cardSuffix",  "type" : "string",  "default" : "NONE",  "doc" : "Last 4 digits of the card." },
        { "name" : "primaryUser",  "type" : "string",  "default" : "NONE",  "doc" : "Boolean as to whether CifKey/AnalyticsId is the Primary Card holder. True or False" },
        { "name" : "authorisedUser",  "type" : "string",  "default" : "NONE",  "doc" : "Boolean as to whether CifKey/AnalyticsId is the Authroised Card holder. True or False" }
    ]
}


# applications (UCWA)

 **Last modified:** July 14, 2015

 _**Applies to:** Skype for Business 2015_

 
Represents the entry point for registering this application with the server. 

## Web Link
<a name="sectionSection0"> </a>

For more on web links, see [Web links](WebLinks.md).



|**Name**|**Description**|
|:-----|:-----|
|rel|The resource that this link points to. In JSON, this is the outer container.|
|href|The location of this resource on the server, and the target of an HTTP operation.|

## Resource description
<a name="sectionSection1"> </a>




### Properties

None


### Links

None


## Operations
<a name="sectionSection2"> </a>




### POST

This very first operation used to create an instance of the application resource. The application resource is the starting point for all applications to discover and navigate all available resources and capabilities of the service.


#### Request body

None


#### Response body



|**Item**|**Description**|
|:-----|:-----|
|[application (UCWA)](application_ref.md)|Represents your real-time communication application.|

#### Synchronous errors

The errors below (if any) are specific to this resource. Generic errors that can apply to any resource are covered in [Generic synchronous errors](GenericSynchronousErrors.md).



|**Error**|**Code**|**Subcode**|**Description**|
|:-----|:-----|:-----|:-----|
|Forbidden|403|None|Forbidden when a federated Office Communications Server 2007 R2 user joins a meeting.|
|Forbidden|403|None|Indicates that user is not allowed to create mobile application.|
|ServiceFailure|500|CallbackChannelError|The remote event channel is not reachable|
|Conflict|409|AlreadyExists|The already exists error.|
|Conflict|409|TooManyGroups|The too many groups error.|
|Conflict|409|None|Un-supported Service/Resource/API error.|

#### Examples




#### JSON Request


```

										Post https://fe1.contoso.com:443//v1/applications HTTP/1.1
										Authorization: Bearer cwt=PHNhbWw6QXNzZXJ0aW9uIHhtbG5...uZm8
										Host: fe1.contoso.com
										Content-Type: application/json
										Accept: application/json
										Content-Length: 120
										{
  "culture" : "en-us",
  "endpointId" : "123456",
  "instanceId" : "samplevalue",
  "userAgent" : "ContosoApp/1.0 (Windows Phone OS 7.5)"
}
									
```


#### JSON Response

This sample is given only as an illustration of response syntax. The semantic content is not guaranteed to correspond to a valid scenario.


```

										HTTP/1.1 201 Created
										Etag: 2dbc6b7a-e659-4cdc-8e08-a0d36dc0680f
										Content-Type: application/json
										Content-Length: 3487
										{
  "rel" : "application",
  "culture" : "en-us",
  "endpointId" : "samplevalue",
  "instanceId" : "samplevalue",
  "userAgent" : "ContosoApp/1.0",
  "_links" : {
    "self" : {
      "href" : "//v1/applications/833"
    },
    "batch" : {
      "href" : "//v1/applications/833/batch"
    },
    "events" : {
      "href" : "http://sample/ucwa/v1/applications/appId/events"
    },
    "policies" : {
      "href" : "//v1/applications/833/policies"
    }
  },
  "_embedded" : {
    "communication" : {
      "simultaneousRingNumberMatch" : "Disabled",
      "rel" : "communication",
      "conversationHistory" : "Disabled",
      "phoneNumber" : "tel:+14255552222",
      "supportedMessageFormats" : [
        "Plain",
        "Html"
      ],
      "supportedModalities" : [
        "PhoneAudio",
        "Messaging"
      ],
      "_links" : {
        "self" : {
          "href" : "//v1/applications/833/communication"
        },
        "conversationLogs" : {
          "href" : "//v1/applications/833/communication/conversationLogs"
        },
        "conversations" : {
          "href" : "//v1/applications/833/communication/conversations"
        },
        "joinOnlineMeeting" : {
          "href" : "//v1/applications/833/communication/joinOnlineMeeting"
        },
        "missedItems" : {
          "href" : "//v1/applications/833/communication/missedItems"
        },
        "startMessaging" : {
          "href" : "//v1/applications/833/communication/startMessaging"
        },
        "startOnlineMeeting" : {
          "href" : "//v1/applications/833/communication/startOnlineMeeting"
        },
        "startPhoneAudio" : {
          "href" : "//v1/applications/833/communication/startPhoneAudio"
        }
      }
    },
    "me" : {
      "rel" : "me",
      "department" : "Sales",
      "emailAddresses" : [
        "johndoe@contoso.com"
      ],
      "name" : "John Doe",
      "title" : "Senior Manager",
      "uri" : "sip:johndoe@contoso.com",
      "_links" : {
        "self" : {
          "href" : "//v1/applications/833/me"
        },
        "callForwardingSettings" : {
          "href" : "//v1/applications/833/me/callForwardingSettings"
        },
        "location" : {
          "href" : "//v1/applications/833/me/location"
        },
        "makeMeAvailable" : {
          "href" : "//v1/applications/833/communication/makeMeAvailable"
        },
        "note" : {
          "href" : "//v1/applications/833/me/note"
        },
        "phones" : {
          "href" : "//v1/applications/833/me/phones"
        },
        "photo" : {
          "href" : "//v1/applications/833/photo"
        },
        "presence" : {
          "href" : "//v1/applications/833/me/presence"
        },
        "reportMyActivity" : {
          "href" : "//v1/applications/833/reportMyActivity"
        }
      }
    },
    "onlineMeetings" : {
      "rel" : "onlineMeetings",
      "_links" : {
        "self" : {
          "href" : "//v1/applications/833/onlineMeetings"
        },
        "myAssignedOnlineMeeting" : {
          "href" : "//v1/applications/833/onlineMeetings/myOnlineMeetings/318"
        },
        "myOnlineMeetings" : {
          "href" : "//v1/applications/833/onlineMeetings/myOnlineMeetings"
        },
        "onlineMeetingDefaultValues" : {
          "href" : "//v1/applications/833/onlineMeetings/onlineMeetingDefaultValues"
        },
        "onlineMeetingEligibleValues" : {
          "href" : "//v1/applications/833/onlineMeetings/onlineMeetingEligibleValues"
        },
        "onlineMeetingInvitationCustomization" : {
          "href" : "//v1/applications/833/onlineMeetings/onlineMeetingInvitationCustomization"
        },
        "onlineMeetingPolicies" : {
          "href" : "//v1/applications/833/onlineMeetings/onlineMeetingPolicies"
        },
        "phoneDialInInformation" : {
          "href" : "//v1/applications/833/onlineMeetings/phoneDialInInformation"
        }
      }
    },
    "people" : {
      "rel" : "people",
      "_links" : {
        "self" : {
          "href" : "//v1/applications/833/people"
        },
        "myContactsAndGroupsSubscription" : {
          "href" : "//v1/applications/833/people/myContactsAndGroupsSubscription"
        },
        "myContacts" : {
          "href" : "//v1/applications/833/contacts"
        },
        "myGroupMemberships" : {
          "href" : "//v1/applications/833/myGroupMemberships"
        },
        "myGroups" : {
          "href" : "//v1/applications/833/groups"
        },
        "myPrivacyRelationships" : {
          "href" : "//v1/applications/833/myPrivacyRelationships"
        },
        "presenceSubscriptionMemberships" : {
          "href" : "//v1/applications/833/presenceSubscriptionMemberships"
        },
        "presenceSubscriptions" : {
          "href" : "//v1/applications/833/presenceSubscriptions"
        },
        "search" : {
          "href" : "//v1/applications/833/search"
        },
        "subscribedContacts" : {
          "href" : "//v1/applications/833/subscribedContacts"
        }
      }
    }
  }
}
									
```


#### XML Request


```

										Post https://fe1.contoso.com:443//v1/applications HTTP/1.1
										Authorization: Bearer cwt=PHNhbWw6QXNzZXJ0aW9uIHhtbG5...uZm8
										Host: fe1.contoso.com
										Content-Type: application/xml
										Accept: application/xml
										Content-Length: 318
										&amp;lt;?xml version=&amp;quot;1.0&amp;quot; encoding=&amp;quot;utf-8&amp;quot;?&amp;gt;
&amp;lt;input xmlns=&amp;quot;http://schemas.microsoft.com/rtc/2012/03/ucwa&amp;quot;&amp;gt;
  &amp;lt;property name=&amp;quot;culture&amp;quot;&amp;gt;en-us&amp;lt;/property&amp;gt;
  &amp;lt;property name=&amp;quot;endpointId&amp;quot;&amp;gt;123456&amp;lt;/property&amp;gt;
  &amp;lt;property name=&amp;quot;instanceId&amp;quot;&amp;gt;samplevalue&amp;lt;/property&amp;gt;
  &amp;lt;property name=&amp;quot;userAgent&amp;quot;&amp;gt;ContosoApp/1.0 (Windows Phone OS 7.5)&amp;lt;/property&amp;gt;
&amp;lt;/input&amp;gt;
									
```


#### XML Response

This sample is given only as an illustration of response syntax. The semantic content is not guaranteed to correspond to a valid scenario.


```

										HTTP/1.1 201 Created
										Etag: 129d6844-0896-49c2-aa86-5f740b70e3ff
										Content-Type: application/xml
										Content-Length: 4371
										&amp;lt;?xml version=&amp;quot;1.0&amp;quot; encoding=&amp;quot;utf-8&amp;quot;?&amp;gt;
&amp;lt;resource rel=&amp;quot;application&amp;quot; href=&amp;quot;//v1/applications/833&amp;quot; xmlns=&amp;quot;http://schemas.microsoft.com/rtc/2012/03/ucwa&amp;quot;&amp;gt;
  &amp;lt;link rel=&amp;quot;batch&amp;quot; href=&amp;quot;//v1/applications/833/batch&amp;quot; /&amp;gt;
  &amp;lt;link rel=&amp;quot;events&amp;quot; href=&amp;quot;http://sample/ucwa/v1/applications/appId/events&amp;quot; /&amp;gt;
  &amp;lt;link rel=&amp;quot;policies&amp;quot; href=&amp;quot;//v1/applications/833/policies&amp;quot; /&amp;gt;
  &amp;lt;property name=&amp;quot;rel&amp;quot;&amp;gt;application&amp;lt;/property&amp;gt;
  &amp;lt;property name=&amp;quot;culture&amp;quot;&amp;gt;en-us&amp;lt;/property&amp;gt;
  &amp;lt;property name=&amp;quot;endpointId&amp;quot;&amp;gt;samplevalue&amp;lt;/property&amp;gt;
  &amp;lt;property name=&amp;quot;instanceId&amp;quot;&amp;gt;samplevalue&amp;lt;/property&amp;gt;
  &amp;lt;property name=&amp;quot;userAgent&amp;quot;&amp;gt;ContosoApp/1.0&amp;lt;/property&amp;gt;
  &amp;lt;resource rel=&amp;quot;communication&amp;quot; href=&amp;quot;//v1/applications/833/communication&amp;quot;&amp;gt;
    &amp;lt;link rel=&amp;quot;conversationLogs&amp;quot; href=&amp;quot;//v1/applications/833/communication/conversationLogs&amp;quot; /&amp;gt;
    &amp;lt;link rel=&amp;quot;conversations&amp;quot; href=&amp;quot;//v1/applications/833/communication/conversations&amp;quot; /&amp;gt;
    &amp;lt;link rel=&amp;quot;joinOnlineMeeting&amp;quot; href=&amp;quot;//v1/applications/833/communication/joinOnlineMeeting&amp;quot; /&amp;gt;
    &amp;lt;link rel=&amp;quot;missedItems&amp;quot; href=&amp;quot;//v1/applications/833/communication/missedItems&amp;quot; /&amp;gt;
    &amp;lt;link rel=&amp;quot;startMessaging&amp;quot; href=&amp;quot;//v1/applications/833/communication/startMessaging&amp;quot; /&amp;gt;
    &amp;lt;link rel=&amp;quot;startOnlineMeeting&amp;quot; href=&amp;quot;//v1/applications/833/communication/startOnlineMeeting&amp;quot; /&amp;gt;
    &amp;lt;link rel=&amp;quot;startPhoneAudio&amp;quot; href=&amp;quot;//v1/applications/833/communication/startPhoneAudio&amp;quot; /&amp;gt;
    &amp;lt;property name=&amp;quot;simultaneousRingNumberMatch&amp;quot;&amp;gt;Disabled&amp;lt;/property&amp;gt;
    &amp;lt;property name=&amp;quot;rel&amp;quot;&amp;gt;communication&amp;lt;/property&amp;gt;
    &amp;lt;property name=&amp;quot;conversationHistory&amp;quot;&amp;gt;Disabled&amp;lt;/property&amp;gt;
    &amp;lt;property name=&amp;quot;phoneNumber&amp;quot;&amp;gt;tel:+14255552222&amp;lt;/property&amp;gt;
    &amp;lt;propertyList name=&amp;quot;supportedMessageFormats&amp;quot;&amp;gt;
      &amp;lt;item&amp;gt;Plain&amp;lt;/item&amp;gt;
      &amp;lt;item&amp;gt;Html&amp;lt;/item&amp;gt;
    &amp;lt;/propertyList&amp;gt;
    &amp;lt;propertyList name=&amp;quot;supportedModalities&amp;quot;&amp;gt;
      &amp;lt;item&amp;gt;PhoneAudio&amp;lt;/item&amp;gt;
      &amp;lt;item&amp;gt;Messaging&amp;lt;/item&amp;gt;
    &amp;lt;/propertyList&amp;gt;
  &amp;lt;/resource&amp;gt;
  &amp;lt;resource rel=&amp;quot;me&amp;quot; href=&amp;quot;//v1/applications/833/me&amp;quot;&amp;gt;
    &amp;lt;link rel=&amp;quot;callForwardingSettings&amp;quot; href=&amp;quot;//v1/applications/833/me/callForwardingSettings&amp;quot; /&amp;gt;
    &amp;lt;link rel=&amp;quot;location&amp;quot; href=&amp;quot;//v1/applications/833/me/location&amp;quot; /&amp;gt;
    &amp;lt;link rel=&amp;quot;makeMeAvailable&amp;quot; href=&amp;quot;//v1/applications/833/communication/makeMeAvailable&amp;quot; /&amp;gt;
    &amp;lt;link rel=&amp;quot;note&amp;quot; href=&amp;quot;//v1/applications/833/me/note&amp;quot; /&amp;gt;
    &amp;lt;link rel=&amp;quot;phones&amp;quot; href=&amp;quot;//v1/applications/833/me/phones&amp;quot; /&amp;gt;
    &amp;lt;link rel=&amp;quot;photo&amp;quot; href=&amp;quot;//v1/applications/833/photo&amp;quot; /&amp;gt;
    &amp;lt;link rel=&amp;quot;presence&amp;quot; href=&amp;quot;//v1/applications/833/me/presence&amp;quot; /&amp;gt;
    &amp;lt;link rel=&amp;quot;reportMyActivity&amp;quot; href=&amp;quot;//v1/applications/833/reportMyActivity&amp;quot; /&amp;gt;
    &amp;lt;property name=&amp;quot;rel&amp;quot;&amp;gt;me&amp;lt;/property&amp;gt;
    &amp;lt;property name=&amp;quot;department&amp;quot;&amp;gt;Sales&amp;lt;/property&amp;gt;
    &amp;lt;propertyList name=&amp;quot;emailAddresses&amp;quot;&amp;gt;
      &amp;lt;item&amp;gt;johndoe@contoso.com&amp;lt;/item&amp;gt;
    &amp;lt;/propertyList&amp;gt;
    &amp;lt;property name=&amp;quot;name&amp;quot;&amp;gt;John Doe&amp;lt;/property&amp;gt;
    &amp;lt;property name=&amp;quot;title&amp;quot;&amp;gt;Senior Manager&amp;lt;/property&amp;gt;
    &amp;lt;property name=&amp;quot;uri&amp;quot;&amp;gt;sip:johndoe@contoso.com&amp;lt;/property&amp;gt;
  &amp;lt;/resource&amp;gt;
  &amp;lt;resource rel=&amp;quot;onlineMeetings&amp;quot; href=&amp;quot;//v1/applications/833/onlineMeetings&amp;quot;&amp;gt;
    &amp;lt;link rel=&amp;quot;myAssignedOnlineMeeting&amp;quot; href=&amp;quot;//v1/applications/833/onlineMeetings/myOnlineMeetings/318&amp;quot; /&amp;gt;
    &amp;lt;link rel=&amp;quot;myOnlineMeetings&amp;quot; href=&amp;quot;//v1/applications/833/onlineMeetings/myOnlineMeetings&amp;quot; /&amp;gt;
    &amp;lt;link rel=&amp;quot;onlineMeetingDefaultValues&amp;quot; href=&amp;quot;//v1/applications/833/onlineMeetings/onlineMeetingDefaultValues&amp;quot; /&amp;gt;
    &amp;lt;link rel=&amp;quot;onlineMeetingEligibleValues&amp;quot; href=&amp;quot;//v1/applications/833/onlineMeetings/onlineMeetingEligibleValues&amp;quot; /&amp;gt;
    &amp;lt;link rel=&amp;quot;onlineMeetingInvitationCustomization&amp;quot; href=&amp;quot;//v1/applications/833/onlineMeetings/onlineMeetingInvitationCustomization&amp;quot; /&amp;gt;
    &amp;lt;link rel=&amp;quot;onlineMeetingPolicies&amp;quot; href=&amp;quot;//v1/applications/833/onlineMeetings/onlineMeetingPolicies&amp;quot; /&amp;gt;
    &amp;lt;link rel=&amp;quot;phoneDialInInformation&amp;quot; href=&amp;quot;//v1/applications/833/onlineMeetings/phoneDialInInformation&amp;quot; /&amp;gt;
    &amp;lt;property name=&amp;quot;rel&amp;quot;&amp;gt;onlineMeetings&amp;lt;/property&amp;gt;
  &amp;lt;/resource&amp;gt;
  &amp;lt;resource rel=&amp;quot;people&amp;quot; href=&amp;quot;//v1/applications/833/people&amp;quot;&amp;gt;
    &amp;lt;link rel=&amp;quot;myContactsAndGroupsSubscription&amp;quot; href=&amp;quot;//v1/applications/833/people/myContactsAndGroupsSubscription&amp;quot; /&amp;gt;
    &amp;lt;link rel=&amp;quot;myContacts&amp;quot; href=&amp;quot;//v1/applications/833/contacts&amp;quot; /&amp;gt;
    &amp;lt;link rel=&amp;quot;myGroupMemberships&amp;quot; href=&amp;quot;//v1/applications/833/myGroupMemberships&amp;quot; /&amp;gt;
    &amp;lt;link rel=&amp;quot;myGroups&amp;quot; href=&amp;quot;//v1/applications/833/groups&amp;quot; /&amp;gt;
    &amp;lt;link rel=&amp;quot;myPrivacyRelationships&amp;quot; href=&amp;quot;//v1/applications/833/myPrivacyRelationships&amp;quot; /&amp;gt;
    &amp;lt;link rel=&amp;quot;presenceSubscriptionMemberships&amp;quot; href=&amp;quot;//v1/applications/833/presenceSubscriptionMemberships&amp;quot; /&amp;gt;
    &amp;lt;link rel=&amp;quot;presenceSubscriptions&amp;quot; href=&amp;quot;//v1/applications/833/presenceSubscriptions&amp;quot; /&amp;gt;
    &amp;lt;link rel=&amp;quot;search&amp;quot; href=&amp;quot;//v1/applications/833/search&amp;quot; /&amp;gt;
    &amp;lt;link rel=&amp;quot;subscribedContacts&amp;quot; href=&amp;quot;//v1/applications/833/subscribedContacts&amp;quot; /&amp;gt;
    &amp;lt;property name=&amp;quot;rel&amp;quot;&amp;gt;people&amp;lt;/property&amp;gt;
  &amp;lt;/resource&amp;gt;
&amp;lt;/resource&amp;gt;
									
```

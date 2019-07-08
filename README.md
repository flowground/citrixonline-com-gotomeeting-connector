# ![LOGO](logo.png) GoToMeeting **flow**ground Connector

## Description

A generated **flow**ground connector for the GoToMeeting API (version 1.0.0).

Generated from: https://api.apis.guru/v2/specs/citrixonline.com/gotomeeting/1.0.0/swagger.json<br/>
Generated at: 2019-07-08T14:35:53+03:00

## API Description

<br>The GoToMeeting API provides seamless integration of GoToMeeting provisioning and meeting management into your existing infrastructure or third party applications.<br><br>For customers, the ability to add, suspend or delete an organizer in your GoToMeeting Corporate account from within your primary management systems simplifies and streamlines the entire process of account management. The ability to monitor meeting schedules, history and active meeting status allows managers to leverage GoToMeeting activities through your primary applications.<br><br>For third parties, the ability to create, update or delete a meeting from within your application makes real-time collaboration possible for your customers. The ability to update meeting schedules, view history and scheduled meetings, and view attendees from past meetings allows you to enhance your users' experience and the value of your applications.<br/>

## Authorization

This API does not require authorization.

## Actions

### Get groups
> List all groups for an account. This API call is only available to users with the admin role.<br/>

*Tags:* `Groups`

#### Input Parameters
* `Authorization` - _required_ - Access token<br/>

### Get attendees by group
> Returns all attendees for all meetings within specified date range held by organizers within the specified group. This API call is only available to users with the admin role. This API call can be used only for groups with maximum 50 organizers.<br/>

*Tags:* `Groups`

#### Input Parameters
* `Authorization` - _required_ - Access token<br/>
* `groupKey` - _required_ - The key of the group<br/>
* `startDate` - _optional_ - Start of date range, in ISO8601 UTC format, e.g. 2015-07-01T22:00:00Z<br/>
* `endDate` - _optional_ - End of date range, in ISO8601 UTC format, e.g. 2015-07-01T23:00:00Z<br/>

### Get historical meetings by group
> Get historical meetings for the specified group that started within the specified date/time range. This API call is only available to users with the admin role. This API call is restricted to groups with a maximum of 50 organizers. Remark: Meetings which are still ongoing at the time of the request are NOT contained in the result array.<br/>

*Tags:* `Groups`

#### Input Parameters
* `Authorization` - _required_ - Access token<br/>
* `groupKey` - _required_ - The key of the group<br/>
* `startDate` - _required_ - Required start of date range, in ISO8601 UTC format, e.g. 2015-07-01T22:00:00Z<br/>
* `endDate` - _required_ - Required end of date range, in ISO8601 UTC format, e.g. 2015-07-01T23:00:00Z<br/>

### DEPRECATED: Get historical meetings by group
> DEPRECATED: Please use the new API calls 'Get historical meetings by group' and 'Get upcoming meetings by group'. Get meetings for a specified group. Additional filters can be used to view only meetings within a specified date range. This API call is only available to users with the admin role.<br/>

*Tags:* `Groups`

#### Input Parameters
* `Authorization` - _required_ - Access token<br/>
* `groupKey` - _required_ - The key of the group<br/>
* `history` - _required_ - When 'true', returns all past meetings within date range<br/>
* `startDate` - _required_ - If history=true, required start of date range, in ISO8601 UTC format, e.g. 2015-07-01T22:00:00Z<br/>
* `endDate` - _required_ - If history=true, required end of date range, in ISO8601 UTC format, e.g. 2015-07-01T23:00:00Z<br/>

### Get organizers by group
> Returns all the organizers within a specific group. This API call is only available to users with the admin role.<br/>

*Tags:* `Groups`

#### Input Parameters
* `Authorization` - _required_ - Access token<br/>
* `groupKey` - _required_ - The key of the group<br/>

### Create organizer in group
> Creates a new organizer and sends an email to the email address defined in request. This API call is only available to users with the admin role. You may also pass 'G2W' or 'G2T' or 'OPENVOICE' as productType variables, creating organizers for those products. A G2W or G2T organizer will also have access to G2M.<br/>

*Tags:* `Groups`

#### Input Parameters
* `Authorization` - _required_ - Access token<br/>
* `groupKey` - _required_ - The key of the group<br/>

### Get upcoming meetings by group
> Get upcoming meetings for a specified group. This API call is only available to users with the admin role. This API call can be used only for groups with maximum 50 organizers.<br/>

*Tags:* `Groups`

#### Input Parameters
* `Authorization` - _required_ - Access token<br/>
* `groupKey` - _required_ - The key of the group<br/>

### Get historical meetings
> Get historical meetings for the currently authenticated organizer that started within the specified date/time range. Remark: Meetings which are still ongoing at the time of the request are NOT contained in the result array.<br/>

*Tags:* `Meetings`

#### Input Parameters
* `Authorization` - _required_ - Access token<br/>
* `startDate` - _required_ - Required start of date range, in ISO8601 UTC format, e.g. 2015-07-01T22:00:00Z<br/>
* `endDate` - _required_ - Required end of date range, in ISO8601 UTC format, e.g. 2015-07-01T23:00:00Z<br/>

### DEPRECATED: Get historical meetings
> DEPRECATED: Please use the new API calls 'Get historical meetings' and 'Get upcoming meetings'.  Gets historical meetings for the current authenticated organizer. Requires date range for filtering results to only meetings within specified dates. History searches will contain the parameter 'meetingInstanceKey' which is used in conjunction with the call 'Get Attendees by Meeting' to get attendee information for a past meeting.<br/>

*Tags:* `Meetings`

#### Input Parameters
* `Authorization` - _required_ - Access token<br/>
* `history` - _optional_ - When 'true', returns all past meetings within date range<br/>
    Possible values: true.
* `startDate` - _optional_ - If history=true, required start of date range, in ISO8601 UTC format, e.g. 2015-07-01T22:00:00Z<br/>
* `endDate` - _optional_ - If history=true, required end of date range, in ISO8601 UTC format, e.g. 2015-07-01T23:00:00Z<br/>

### Create meeting
> Create a new meeting based on the parameters specified.<br/>

*Tags:* `Meetings`

#### Input Parameters
* `Authorization` - _required_ - Access token<br/>

### Delete meeting
> Deletes the meeting identified by the meetingId.<br/>

*Tags:* `Meetings`

#### Input Parameters
* `Authorization` - _required_ - Access token<br/>
* `meetingId` - _required_ - The meeting ID<br/>

### Get meeting
> Returns the meeting details for the specified meeting.<br/>

*Tags:* `Meetings`

#### Input Parameters
* `Authorization` - _required_ - Access token<br/>
* `meetingId` - _required_ - The meeting ID<br/>

### Update meeting
> Updates an existing meeting specified by meetingId.<br/>

*Tags:* `Meetings`

#### Input Parameters
* `Authorization` - _required_ - Access token<br/>
* `meetingId` - _required_ - The meeting ID<br/>

### Get attendees by meeting
> List all attendees for specified meetingId of historical meeting. The historical meetings can be fetched using 'Get historical meetings', 'Get historical meetings by organizer', and 'Get historical meetings by group'. For users with the admin role this call returns attendees for any meeting. For any other user the call will return attendees for meetings on which the user is a valid organizer.<br/>

*Tags:* `Meetings`

#### Input Parameters
* `Authorization` - _required_ - Access token<br/>
* `meetingId` - _required_ - The meeting ID<br/>

### Start meeting
> Returns a host URL that can be used to start a meeting. When this URL is opened in a web browser, the GoToMeeting client will be downloaded and launched and the meeting will start. The end user is not required to login to a client.<br/>

*Tags:* `Meetings`

#### Input Parameters
* `Authorization` - _required_ - Access token<br/>
* `meetingId` - _required_ - The meeting ID<br/>

### Delete organizer by email
> Deletes the individual organizer specified by the email address. This API call is only available to users with the admin role.<br/>

*Tags:* `Organizers`

#### Input Parameters
* `Authorization` - _required_ - Access token<br/>
* `email` - _required_ - The email address of the organizer<br/>

### Get organizer by email / Get all organizers
> Gets the individual organizer specified by the organizer's email address. If an email address is not specified, all organizers are returned. This API call is only available to users with the admin role.<br/>

*Tags:* `Organizers`

#### Input Parameters
* `Authorization` - _required_ - Access token<br/>
* `email` - _optional_ - The email address of the organizer<br/>

### Create organizer
> Creates a new organizer and sends an email to the email address defined in the request. This API call is only available to users with the admin role. You may also pass 'G2W' or 'G2T' or 'OPENVOICE' as productType variables, creating organizers for those products. A G2W or G2T organizer will also have access to G2M.<br/>

*Tags:* `Organizers`

#### Input Parameters
* `Authorization` - _required_ - Access token<br/>

### Delete organizer
> Deletes the individual organizer specified by the organizer key. This API call is only available to users with the admin role.<br/>

*Tags:* `Organizers`

#### Input Parameters
* `Authorization` - _required_ - Access token<br/>
* `organizerKey` - _required_ - The key of the organizer<br/>

### Get organizer
> Returns the individual organizer specified by the key. This API call is only available to users with the admin role. Non-admin users can only make this call for their own organizerKey.<br/>

*Tags:* `Organizers`

#### Input Parameters
* `Authorization` - _required_ - Access token<br/>
* `organizerKey` - _required_ - The key of the organizer<br/>

### Update organizer
> Updates the products of the specified organizer. To add a product (G2M, G2W, G2T, OPENVOICE) for the organizer, the call must be sent once for each product you want to add. To remove all products for the organizer, set status to 'suspended'. The call is limited to users with the admin role.<br/>

*Tags:* `Organizers`

#### Input Parameters
* `Authorization` - _required_ - Access token<br/>
* `organizerKey` - _required_ - The key of the organizer<br/>

### Get attendees by organizer
> Lists all attendees for all meetings within a specified date range for a specified organizer. This API call is only available to users with the admin role.<br/>

*Tags:* `Organizers`

#### Input Parameters
* `Authorization` - _required_ - Access token<br/>
* `organizerKey` - _required_ - The key of the organizer<br/>
* `startDate` - _required_ - A required start of date range in ISO8601 UTC format, e.g. 2015-07-01T22:00:00Z<br/>
* `endDate` - _required_ - A required end of date range in ISO8601 UTC format, e.g. 2015-07-01T23:00:00Z<br/>

### Get historical meetings by organizer
> Get historical meetings for the specified organizer that started within the specified date/time range. Remark: Meetings which are still ongoing at the time of the request are NOT contained in the result array.<br/>

*Tags:* `Organizers`

#### Input Parameters
* `Authorization` - _required_ - Access token<br/>
* `organizerKey` - _required_ - The key of the organizer<br/>
* `startDate` - _required_ - Required start of date range, in ISO8601 UTC format, e.g. 2015-07-01T22:00:00Z<br/>
* `endDate` - _required_ - Required end of date range, in ISO8601 UTC format, e.g. 2015-07-01T23:00:00Z<br/>

### DEPRECATED: Get meetings by organizer
> DEPRECATED: Please use the new API calls 'Get historical meetings by organizer' and 'Get upcoming meetings by organizer'. Gets future (scheduled) or past (history) meetings for a specified organizer. Include 'history=true' and the past start and end dates in the URL to retrieve past meetings. Enter 'scheduled=true' (without dates) to get scheduled meetings.<br/>

*Tags:* `Organizers`

#### Input Parameters
* `Authorization` - _required_ - Access token<br/>
* `organizerKey` - _required_ - The key of the organizer<br/>
* `scheduled` - _optional_ - When 'true', returns all future meetings. Date range not supported.<br/>
* `history` - _optional_ - When 'true', returns all past meetings within date range<br/>
* `startDate` - _optional_ - If history is 'true', required start of date range, in ISO8601 UTC format, e.g. 2015-07-01T22:00:00Z<br/>
* `endDate` - _optional_ - If history is 'true', required end of date range, in ISO8601 UTC format, e.g. 2015-07-01T23:00:00Z<br/>

### Get upcoming meetings by organizer
> Get upcoming meetings for a specified organizer. This API call is only available to users with the admin role.<br/>

*Tags:* `Organizers`

#### Input Parameters
* `Authorization` - _required_ - Access token<br/>
* `organizerKey` - _required_ - The key of the organizer<br/>

### Get upcoming meetings
> Gets upcoming meetings for the current authenticated organizer.<br/>

*Tags:* `Meetings`

#### Input Parameters
* `Authorization` - _required_ - Access token<br/>

## License

**flow**ground :- Telekom iPaaS / citrixonline-com-gotomeeting-connector<br/>
Copyright © 2019, [Deutsche Telekom AG](https://www.telekom.de)<br/>
contact: flowground@telekom.de

All files of this connector are licensed under the Apache 2.0 License. For details
see the file LICENSE on the toplevel directory.

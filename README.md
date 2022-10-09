# KDAV

## Introduction

This is an DAV protocol implementation with KJobs.

Calendars and todos are supported, using either GroupDAV
or CalDAV, and contacts are supported using GroupDAV or
CardDAV.


## Usage

It should be pretty straightforward. The URL to use should be, if possible,
the principals URL for your server (CalDAV / CardDAV) or the parent
collection of your calendars to allow discovery.


## Tested with / known bugs

Here is a list of servers tested with this resource with the URLs used.
Feel free to contact the author(s) if you successfully tested a configuration
not listed here.

* Egroupware (1.6.002)
  https://host/groupdav.php
  - GroupDAV working.
  - CalDAV working.
  - CardDAV working.

* SOGo (version 1.0.4, 1.1.0 and version at http://sogo-demo.inverse.ca/)
  https://host/SOGo/dav/<USER>/Calendar and https://host/SOGo/dav/<USER>/Contacts
  - GroupDAV calendar working, but the timezone data in the ICalendar
    generated by KCal seems misinterpreted by SOGo : every event is
    shifted by the timezone offset (at least test with TZ Europe/Paris,
    feel free to send your results to the author(s). This seems resolved
    with the demo version made available by Inverse.ca.
  - CalDAV working, with the same bug.
  - CardDAV working.

* Davical (version 0.9.7.6)
  https://host/caldav.php/principals/users/<USER>
  - CalDAV working.

* Zimbra Open-Source edition (version 5.0.18),
  https://host/principals/users/<USER>
  - Caldav mostly working : retrieval of shared calendars that contain a lot
    of events fails with a 500 server error.

* Google calendar
  https://www.google.com/calendar/dav/<CALENDAR_ID>/events
  - CalDAV working.
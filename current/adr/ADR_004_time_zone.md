# Title

Guidelines for the use of time zones

## Status

**accepted**

## Context

The application must work internationally. The application user is travelling all over the world.  
There is always some confusion how to support time in distributed applications across multiple timezones. Is it better to use local user time or based on UTC universal time?

## Decision

We decided to use Coordinated Universal Time (UTC) for the whole backend system spreaded across multiple datacenters to facilitate the process of synchronization and data management on the server side. This approach reduces the likelihood of making an error when processing time data.

We decided to use local user time for user application interface to not cause confusion for application users. People operate in their local time zone. The user application interface should have functionality to change the time zone to one the traveller is currenty located.

## Consequences

All databases and operation systems must UTC time set as default and working in it.  

The UTC time is transformed to local user time when shown in user application interface.  

The time format must include time zone as well.  

The data synchronization application do not transform time between timezones when replicates travelling data.
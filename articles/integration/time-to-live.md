---
title: Expire data in Chorus with Time to Live 
description: With TTL, Chorus provides the ability to have documents automatically purged from the system after a period of time.
author: richf

---
# Time to Live (TTL) in Chorus 

With **Time to Live** or TTL, Chorus provides the ability to delete items automatically for a Publisher after a certain time period. By default [Actors](actor.md), [Groups](group.md), and [Users](user.md) are subject to [data privacy regulations](data-privacy.md) and will never expire unless explicitly prohibited. [Data feed](actor-data-feed.md) expirations can vary from five minutes to one year. Chorus automatically expires and deletes items based on the last modification and interval specified for the TTL (seconds).

Deletion of expired items is a background task that consumes left-over [Request Units](request-units.md) (RU), that is Request Units that haven't been consumed by requests. Even after the TTL has expired, if Chorus is overloaded with requests and if there are not enough RU's available, the data deletion is delayed. Data is deleted once there are enough RUs available to perform the delete operation. Although data deletion is delayed, Chorus does not return data after the TTL has expired.

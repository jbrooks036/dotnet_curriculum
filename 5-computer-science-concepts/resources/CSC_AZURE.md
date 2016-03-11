# Azure

#### All of this is from Sonda's notes

##### Road to the Cloud Talk:
* In the old old days, you had an office building with the fastest internet you could find.  And in that building, you had a server closet, with actual server(s) in it.  The server is connected to the outside world via a DSL line and has a static IP address.
This is dumb.  Expensive.  High electric bill.
* Then comes colo’s (co-locations).  This is still fairly “old days”.  Essentially racks of servers - smaller server farms.  You can rent a server there, or put your server there, like a server apartment complex.
* The next level up is a data-center.  It’s like a colo, but it’s big and you own it.  Like, a whole damn building full of servers.  Problem is, imagine Amazon, in order to have the number of machines necessary to store the data required for peak capacity (say, Christmas) - you have to deal with a lot of those machines sitting idle when it’s not peak season.
* What Amazon then did after awhile, was rent out the machines they weren’t using.  Essentially renting out excess capacity that otherwise would have been sitting there unused.  
* When you are seeing cloud hardware, it actually falls asleep one place and then wakes up another place each time you have downtime because the location is not saved.  For instance, the stuff you have stored could have been on rack 26 on floor 2, then falls asleep, and wakes up on rack 17 on floor 1.
* In the world of Microsoft, we have Azure instead of Amazon’s AWS.

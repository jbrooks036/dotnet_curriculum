# Memory Fundamentals

### Garbage Collectors (per Sonda's notes)

* part of language that cleans up any objects that aren’t being used to make the program more efficient and frees up memory.

* **Mark and Sweep** - It’s a "stop the world" (freezes the program for a moment) to mark all the variables that are being used and follow their relationships and marks them. Then it goes back and sweeps away all the items that are not marked.

*	**Relational Counting** - while an item is being created, it keeps track of the number of things being pointed to it. When an item has a zero number of things pointing to it, then the collector deletes it on the fly. This is a more sophisticated sweeping methods, but more prone to mistakes, too.

---
title: Making query cache contention more obvious
date: "2010-09-15"
url: /blog/2010/09/15/making-query-cache-contention-more-obvious/
categories:
  - Databases
---
The [newest release of Percona Server](http://www.mysqlperformanceblog.com/2010/09/15/percona-server-5-1-49-rel12-0/) includes a trivial change that I think will be extremely valuable. This is the addition of a new thread state, "Waiting on query cache mutex." Fixing the query cache to make it scalable is hard. Fixing the server to report when the query cache is a bottleneck is not hard. It has historically been very difficult for users to diagnose what's wrong with their server when the query cache is locking it intermittently. Now it will be trivial: they will look at SHOW PROCESSLIST and the evidence will be unmistakable.



# Overview
This nginx demonstrates
* sharded lookup using smart content-based routers
* sharded upload of content
* handling of cache misses - currently we generate fake content and proxy directly to the content uploader

# Demo
## Hit an existing page
Here we get content back:
```
% curl "http://54.151.101.216:8080/?url=abc"    
abc
```

## Hit a non-existing page
Here we get a fancy 404 message back.  Note that if the page is already there, try another random string for the `url` query param
```
% curl "http://54.151.101.216:8080/?url=abcdefgh"
8082: Your page was not found, check again later, we're writing it to disk...
pageUrl=abcdefgh
hash=e8dc4081
pageContent=
This is a generated page for testing.
pageUrl=abcdefgh
hash=e8dc4081

filename=/home/ubuntu/work/cache/8082/e8dc4081

```

Now hit the same page again.  We get a hit since it's been written to disk.
```
% curl "http://54.151.101.216:8080/?url=abcdefgh"
This is a generated page for testing.
pageUrl=abcdefgh
hash=e8dc4081
```

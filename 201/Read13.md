
### Article [THE PAST, PRESENT & FUTURE OF LOCAL STORAGE FOR WEB APPLICATIONS](http://diveinto.html5doctor.com/storage.html)

#### I learned from this article

1.  Cookies were invented early in the web’s history, and they can be used for persistent local storage of small amounts of data. But they have three potentially dealbreaking downsides:
    - Cookies are included with every HTTP request, thereby slowing down your web application by needlessly transmitting the same data over and over
    - Cookies are included with every HTTP request, thereby sending data unencrypted over the internet
    - Cookies are limited to about 4 KB of data — enough to slow down your application (see above), but not enough to be terribly useful
1. userData allows web pages to store up to 64 KB of data per domain
1.  Local Shared Objects. It allows Flash objects to store up to 100 KB of data per domain.
1. Gears provides an API to an embedded SQL database based on SQLite. After obtaining permission from the user once, Gears can store unlimited amounts of data per domain in SQL database tables.
1. HTML5 Storage is a way for web pages to store named key/value pairs locally, within the client web browser. 
1. If you are storing and retrieving anything other than strings, you will need to use functions like parseInt() or parseFloat() to coerce your retrieved data into the expected JavaScript datatype.
1. Like other JavaScript objects, you can treat the localStorage object as an associative array. Instead of using the getItem() and setItem() methods, you can simply use square brackets. For example, this snippet of code
1. Calling removeItem() with a non-existent key will do nothing.
1.  if you set an item to its existing value or call clear() when there are no named keys, the storage event will not fire, because nothing actually changed in the storage area.
1.  limitations of the HTML5 Storage
    - “5 megabytes” is how much storage space each origin gets by default. 
    - “QUOTA_EXCEEDED_ERR” is the exception that will get thrown if you exceed your storage quota of 5 megabytes.


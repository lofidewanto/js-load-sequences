# js-load-sequences
Example for JS Load Sequences

The situation:

    I have a JS file "load-test.nocache.js" on server "server-a".
    On "server-b" I have an HTML file and I use the JS file from "server-a".

Something like index.html on "server-b":


```
<script src="https://server-a.de/load-test.nocache.js"></script>

<script src="hello.js"></script>
...
...

```

The problem:

    "server-a" got a problem and the index.html tries to fetch the
    test.nocache.js but it takes very long. Timeout is about 4 minutes.
    So the whole parsing doesn't work and the index.html stucks.
    I tried "defer" but at the end still it waits until the timeout.

The question:

    Is there any possibilities that I could fetch the test.nocache.js
    (on server-a) independently from the others?
    As I understood GWT uses iframe to make this happens. But for my case
    it doesn't help since the JS is on the "server-a" and not the
    same server.

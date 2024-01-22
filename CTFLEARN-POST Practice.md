# POST Practice 
https://ctflearn.com/challenge/114

### DESCRIPTION
This website requires authentication, via POST. However, it seems as if someone has defaced our site. Maybe there is still some way to authenticate?

# SOLUTION
From the description alone we understand what is the challenge about. Make a POST request, and pass login information, the question is how it should look like and
what information we need to pass.

![image](https://github.com/W4W1R3/WEB-CHALLS/assets/57982315/d1c156ac-7560-46b8-ace0-7633d67261ab)


In the page we don't see much, checking the source will give us the credentials for the login.

![image](https://github.com/W4W1R3/WEB-CHALLS/assets/57982315/c68ea016-e70e-4f44-97bf-cb18d2964075)

    ` username: admin | password: 71urlkufpsdnlkadsf`
    
So now we know what are the parameters we need to send, and what are their values

### With Python and requests
First I solved it with python and the requests module so I will show it's solution.
```
import requests
url = "http://165.227.106.113/post.php"
d = {"username": "admin", "password": "71urlkufpsdnlkadsf"}
r = requests.post(url, data = d)
print(r.text)
```
File p.py

~~~
╰─ python3 p.py                                                                                                                                                                                                           ─╯
<h1>flag{p0st_d4t4_4ll_d4y}</h1>
~~~

### With curl
`curl  "http://165.227.106.113/post.php" -d "username=admin&password=71urlkufpsdnlkadsf"`

Comparing it to python, this is indeed much faster to make and execute

* `curl` is of course the program we run
* Next is the url, which doesn't have to be at the begging, `curl  -d "username=admin&password=71urlkufpsdnlkadsf" "http://165.227.106.113/post.php"` this would also
work
* `-d` for data, this will also automaticly inform `curl` that this is POST requests (GET doens't have body).
* The data of the Post request.


~~~
╰─ curl  "http://165.227.106.113/post.php" -d "username=admin&password=71urlkufpsdnlkadsf"               ─╯
<h1>flag{p0st_d4t4_4ll_d4y}</h1>%            
~~~

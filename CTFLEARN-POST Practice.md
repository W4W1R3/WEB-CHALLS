# POST Practice 
https://ctflearn.com/challenge/114

### DESCRIPTION
This website requires authentication, via POST. However, it seems as if someone has defaced our site. Maybe there is still some way to authenticate?

# SOLUTION
From the description alone we understand what is the challenge about. Make a POST request, and pass login information, the question is how it should look like and
what information we need to pass.

![image](https://github.com/W4W1R3/WEB-CHALLS/assets/57982315/42634cfc-02af-4ff6-88dc-01c30f2eeb12)

In the page we don't see much, checking the source will give us the credentials for the login.

![image](https://github.com/W4W1R3/WEB-CHALLS/assets/57982315/c68ea016-e70e-4f44-97bf-cb18d2964075)

    ` username: admin | password: 71urlkufpsdnlkadsf`
    
So now we know what are the parameters we need to send, and what are their values



     

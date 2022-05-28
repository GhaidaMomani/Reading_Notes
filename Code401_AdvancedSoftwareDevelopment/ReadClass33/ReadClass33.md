# Reading_Notes
## Code 401 - Advanced Software Development





By [Ghaida Al Momani] (https://github.com/GhaidaMomani).


<br/>
<hr/>
<br/>

# Authentication & Production Server

## How to Use JWT Authentication with Django REST Framework
[Link to the article](https://simpleisbetterthancomplex.com/tutorial/2018/12/19/how-to-use-jwt-authentication-with-django-rest-framework.html)

How the JWT works?
![](../assests/jwt.png)





The JWT is just an authorization token that should be included in all requests:
```py
curl http://127.0.0.1:8000/hello/ -H 'Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ0b2tlbl90eXBlIjoiYWNjZXNzIiwiZXhwIjoxNTQzODI4NDMxLCJqdGkiOiI3ZjU5OTdiNzE1MGQ0NjU3OWRjMmI0OTE2NzA5N2U3YiIsInVzZXJfaWQiOjF9.Ju70kdcaHKn1Qaz8H42zrOYk0Jx9kIckTn9Xx7vhikY'
```
The JWT is acquired by exchanging an username + password for an access token and an refresh token.

The access token is usually short-lived (expires in 5 min or so, can be customized though).

The refresh token lives a little bit longer (expires in 24 hours, also customizable). It is comparable to an authentication session. After it expires, you need a full login with username + password again.

Why is that?

It’s a security feature and also it’s because the JWT holds a little bit more information. If you look closely the example I gave above, you will see the token is composed by three parts:


```
header.payload.signature
```



## Installation & Setup
For this tutorial we are going to use the djangorestframework_simplejwt library, recommended by the DRF developers.

pip install djangorestframework_simplejwt
settings.py

```py
REST_FRAMEWORK = {
    'DEFAULT_AUTHENTICATION_CLASSES': [
        'rest_framework_simplejwt.authentication.JWTAuthentication',
    ],
}
```
urls.py

```py
from django.urls import path
from rest_framework_simplejwt import views as jwt_views

urlpatterns = [
    # Your URLs...
    path('api/token/', jwt_views.TokenObtainPairView.as_view(), name='token_obtain_pair'),
    path('api/token/refresh/', jwt_views.TokenRefreshView.as_view(), name='token_refresh'),
]
```

<hr/>
<p align="right">(<a href="#top">back to top</a>)</p>




# Django Runserver Is Not Your Production Server

You’ve built your Django web app and are working on deploying it.

***You’ve been running your app locally with python manage.py runserver. That’s a fine command, built for development convenience, but it’s not meant to be used as part of a production setup.***

The docs are very adamant about this:

DO NOT USE THIS SERVER IN A PRODUCTION SETTING. It has not gone through security audits or performance tests.

So the server started with runserver is not guaranteed to be performant (it’s very slow), and it hasn’t been built with security concerns in mind. Not a good fit for production use.

So, what’s the right way to approach this?
A Production Stack
You want to only use tech in production, which is reliable, well tested and has been around for a while.

A production setup usually consists of multiple components, each designed and built to be really good at one specific thing. They are fast, reliable and very focused.

When a request arrives at your server, it should be passed to a dedicated web server. Nginx is an example for a good web server.

![](/Code401_AdvancedSoftwareDevelopment/assests/wsgi.png)


<hr/>
<p align="right">(<a href="#top">back to top</a>)</p>


# What is JSON Web Token?
JSON Web Token (JWT) is an open standard (RFC 7519) that defines a compact and self-contained way for securely transmitting information between parties as a JSON object. This information can be verified and trusted because it is digitally signed. JWTs can be signed using a secret (with the HMAC algorithm) or a public/private key pair using RSA or ECDSA.


![](/Code401_AdvancedSoftwareDevelopment/assests/xdc4axtmpwsut743q2s2.png)



## When should you use JSON Web Tokens?


Here are some scenarios where JSON Web Tokens are useful:

Authorization: This is the most common scenario for using JWT. Once the user is logged in, each subsequent request will include the JWT, allowing the user to access routes, services, and resources that are permitted with that token. Single Sign On is a feature that widely uses JWT nowadays, because of its small overhead and its ability to be easily used across different domains.

Information Exchange: JSON Web Tokens are a good way of securely transmitting information between parties. Because JWTs can be signed—for example, using public/private key pairs—you can be sure the senders are who they say they are. Additionally, as the signature is calculated using the header and the payload, you can also verify that the content hasn't been tampered with.








<hr/>
<p align="right">(<a href="#top">back to top</a>)</p>
<br/><br/>
<p align="right">Ghaida Al Momani, Software Engineer</p>
<p align="right">Jordan, Amman</p>
  <p align="right">22, 28 May </p>
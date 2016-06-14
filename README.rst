Tornado-HttpClient-Session
==========================

**Update 2016-06-14: tornado-httpclient-session has vanished from PyPi. This is a fork of Saaj, with the cached data from the official PyPi package merged for backwards compatibility. From the original metadata:**

```
Metadata-Version: 2.0
Name: tornado-httpclient-session
Version: 0.2.1
Summary: Session support to tornado.httpclient.
Home-page: https://github.com/mailto1587/tornado-httpclient-session
Author: mailto1587
Author-email: mailto1587@gmail.com
License: http://opensource.org/licenses/MIT
Keywords: Tornado,HttpClient,Session
Platform: UNKNOWN
Classifier: Programming Language :: Python :: 2
Classifier: Programming Language :: Python :: 3
Requires-Dist: tornado
```

Old info
----

A mimic inspired by the session feature in `Requests <https://github.com/kennethreitz/requests>`_, 
it adds support to `Tornado <https://github.com/tornadoweb/tornado>`_ that allows you to persist 
context such as cookies and other parameters across requests' fetching from 
`tornado.httpclient <http://tornado.readthedocs.org/en/latest/httpclient.html>`_.

**THIS IS SESSION ABOUT CLIENT, NOT SERVER!**

Installation
------------

    pip install tornado-httpclient-session

Usage
-----

.. code-block:: python

   from tornado.httpclient import HTTPClient

   from httpclient_session import Session

   s = Session(HTTPClient) # AsyncHTTPClient default

   r = s.fetch('https://github.com')
   print(r.headers['set-cookie']) # Inspect cookies returnd from Github

   r = s.fetch('https://github.com') # Fetching carrys cookies
   print(r.request.headers['cookie']) # Inspect cookies attached

Testing
-------

    python setup.py test
    
Or for all supported environments:

    tox

Development Progress
--------------------

Persistences of:

* Cookies ✔
* Referrer ✘
* Authorization ✘

Any Suggestions Welcome!
------------------------

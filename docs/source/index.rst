.. httpcache documentation master file, created by
   sphinx-quickstart on Fri May 17 19:58:08 2013.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

httpcache: Caching for Python Requests
======================================

Love `Requests <http://python-requests.org/>`_? Wish it had HTTP caching? Well
then, this is the project for you.

Built from the ground up for combining with your favourite HTTP library, this
library provides totally transparent HTTP caching. Fully RFC 2616-compliant,
no muss, no fuss. Just plug in and go.

::

    >>> import requests
    >>> from httpcache import CachingHTTPAdapter
    >>> s = requests.Session()
    >>> s.mount('http://', CachingHTTPAdapter())
    >>> s.mount('https://', CachingHTTPAdapter())

Any request passed through that session will automatically use the HTTP cache.
Guess what? Requests just got better.

If this library doesn't float your boat, you can also take a look at the
excellent `CacheControl <https://github.com/ionrock/cachecontrol>`_ library,
which directly ports httplib2's caching algorithms.

Features
--------

httpcache fully supports HTTP/1.1 caching, and ties deep into Requests. That
means:

- Supports ``Expires`` headers.
- Supports ``Cache-Control`` headers.
- Understands ``304 Not Modified`` responses.
- Can do validation caching, i.e. ``If-Modified-Since`` headers.
- Correctly navigates the waters of HTTP verbs and urls.
- Fully supports RFC 2616.

Caching with Requests should be as easy as HTTP with Requests. Stop worrying
about it. Just benefit from it.

Versions
--------

httpcache supports all the versions of Python that Requests supports. We intend
to do this indefinitely. Currently, this means we support 2.6, 2.7 and 3.3. It
is possible that httpcache functions on earlier versions of Python, but such
functionality is not supported and may be broken in any version change.

Contents
--------

.. toctree::
   :maxdepth: 2

   quickstart
   api
   contributing

.. meta::
    :tags: gfw, autoproxy

###################################
Writing AutoProxy rules by examples
###################################

https://web.archive.org/web/20110520103723/https://autoproxy.org/rules

Matching keyword with in HTTP URL
=================================

``example.com``

*   Matching:

    *   http\ ://www.\ **example.com**\ /foo
    *   http\ ://www.\ google.com/search?q=www.\ **example.com**

*   Not matching:

    *   https\ ://www.\ **example.com**\ /

Matching HTTP/HTTPS (second-level) domain
=========================================

``||example.com``

*   Matching:

    *   http\ ://\ **example.com**\ /foo
    *   https\ ://subdomain.\ **example.com**\ /bar

*   Not matching:

    *   http\ ://www.\ google.com/search?q=\ **example.com**

Matching URL prefix
===================

``|https://ssl.example.com``

*   Matching:

    *   All domains begins with ``https://ssl.example.com``

``|http://example.com``

*   Matching:

    *   All domains begins with ``http://example.com``

*   Note: used for short link services like http://t.co.

Regex
===================
``/^https?:\/\/[^\/]+example\.com/``


Force no-proxy with "@@"
===================
``@@||no-proxy.com``

* For all entries that match the "||no-proxy.com" rule , don't use proxy

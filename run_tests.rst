+++++++++
Run tests
+++++++++

Introduce a Bug
===============

Instead of trying to write new code, let's start by writing a bug!

Diff::

    diff --git a/Lib/http/server.py b/Lib/http/server.py
    index b1151a2..f132be4 100644
    --- a/Lib/http/server.py
    +++ b/Lib/http/server.py
    @@ -965,6 +965,7 @@ class CGIHTTPRequestHandler(SimpleHTTPRequestHandler):
         rbufsize = 0

         def do_POST(self):
    +        bug
             """Serve a POST request.

             This is only implemented for CGI scripts.


Run tests
=========

Type::

    $ ./python -m test -v test_httpservers

We expect that tests fail::

    (...)
    ======================================================================
    ERROR: test_post (test.test_httpservers.CGIHTTPServerTestCase)
    ----------------------------------------------------------------------
    Traceback (most recent call last):
      File "/home/haypo/prog/python/master/Lib/test/test_httpservers.py", line 726, in test_post
        res = self.request('/cgi-bin/file2.py', 'POST', params, headers)
      File "/home/haypo/prog/python/master/Lib/test/test_httpservers.py", line 79, in request
        return self.connection.getresponse()
      File "/home/haypo/prog/python/master/Lib/http/client.py", line 1322, in getresponse
        response.begin()
      File "/home/haypo/prog/python/master/Lib/http/client.py", line 296, in begin
        version, status, reason = self._read_status()
      File "/home/haypo/prog/python/master/Lib/http/client.py", line 265, in _read_status
        raise RemoteDisconnected("Remote end closed connection without"
    http.client.RemoteDisconnected: Remote end closed connection without response

    ----------------------------------------------------------------------
    (...)
    FAILED (errors=1)
    (...)

Re-run only the failing method::

    $ ./python -m test -v -m test_post test_httpservers

Find the code of the failing tests, see most recent call in the traceback::

      File "/home/haypo/prog/python/master/Lib/test/test_httpservers.py", line 726, in test_post
        res = self.request('/cgi-bin/file2.py', 'POST', params, headers)

Open Lib/test/test_httpservers.py line 726::

    def test_post(self):
        params = urllib.parse.urlencode(
            {'spam' : 1, 'eggs' : 'python', 'bacon' : 123456})
        headers = {'Content-type' : 'application/x-www-form-urlencoded'}
        res = self.request('/cgi-bin/file2.py', 'POST', params, headers)

        self.assertEqual(res.read(), b'1, python, 123456' + self.linesep)


Fix the bug
===========

* Modify Lib/http/server.py to remove ``bug``.
* Re-run test_post() test

Run the whole test suite
========================

* Re-run all test_httpservers tests
* Run the whole test suite

Run the whole test suite::

    ./python -m test -j0 -rW

Flags:

* -j0: run tests in parallel using as many test processes than your CPUs
* -r: randomize tests
* -W: hide test output on success, but write tests output on failure

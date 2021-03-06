Introduction
============

This 'book' is a small set of tutorials about using :term:`libuv` as
a high performance evented I/O library which offers the same API on Windows and Unix and TODO

It is meant to cover the main areas of libuv, but is not a comprehensive
reference discussing every function and data structure.

Who this book is for
--------------------

If you are reading this book, you are either:

1) a systems programmer, creating low-level programs such as daemons or network
   services and clients. You have found that the event loop approach is well
   suited for your application and decided to use libuv.

2) a node.js module writer, who wants to wrap platform APIs
   written in C or C++ with a set of (a)synchronous APIs that are exposed to
   JavaScript. You will use libuv purely in the context of node.js. For
   this you will require some other resources as the book does not cover parts
   specific to v8/node.js.

This book assumes that you are comfortable with the C programming language.

Background
----------

The :term:`node.js` project began in 2009 as a JavaScript environment decoupled
from the browser. Using Google's V8 and Marc Lehmann's libev (TODO: links),
node.js combined a model of I/O -- evented -- with a language that was well
suited to the style of programming; due to the way it had been shaped by
browsers. As node.js grew in popularity, it was important to make it work on
Windows, but libev ran only on Unix. The Windows equivalent of kernel event
notification mechanisms like kqueue or (e)poll is IOCP. libuv is an abstraction
around libev or IOCP depending on the platform, providing users an API based on
libev.

Code
----

All the code from this book is included as part of the source of the book on
Github. `Clone`_/`Download`_ the book and run ``make`` in the ``code/``
folder to compile all the examples. This book and the code is based on libuv
version `node-v0.8.0` and a version is included in the ``libuv/`` folder
which will be compiled automatically.

.. _Clone: https://github.com/nikhilm/uvbook
.. _Download: https://github.com/nikhilm/uvbook/downloads
.. _node-v0.8.0: https://github.com/joyent/libuv/tags

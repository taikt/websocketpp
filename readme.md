WebSocket++ (0.8.2)
==========================

WebSocket++ is a header only C++ library that implements RFC6455 The WebSocket
Protocol. It allows integrating WebSocket client and server functionality into
C++ programs. It uses interchangeable network transport modules including one
based on raw char buffers, one based on C++ iostreams, and one based on Asio 
(either via Boost or standalone). End users can write additional transport
policies to support other networking or event libraries as needed.

Major Features
==============
* Full support for RFC6455
* Partial support for Hixie 76 / Hybi 00, 07-17 draft specs (server only)
* Message/event based interface
* Supports secure WebSockets (TLS), IPv6, and explicit proxies.
* Flexible dependency management (C++11 Standard Library or Boost)
* Interchangeable network transport modules (raw, iostream, Asio, or custom)
* Portable/cross platform (Posix/Windows, 32/64bit, Intel/ARM/PPC)
* Thread-safe

Get Involved
============

[![Build Status](https://travis-ci.org/zaphoyd/websocketpp.png)](https://travis-ci.org/zaphoyd/websocketpp)

**Project Website**
http://www.zaphoyd.com/websocketpp/

**User Manual**
http://docs.websocketpp.org/

**GitHub Repository**
https://github.com/zaphoyd/websocketpp/

GitHub pull requests should be submitted to the `develop` branch.

**Announcements Mailing List**
http://groups.google.com/group/websocketpp-announcements/

**IRC Channel**
 #websocketpp (freenode)

**Discussion / Development / Support Mailing List / Forum**
http://groups.google.com/group/websocketpp/

** [taikt] 

-- How to build

cd websocketpp/
sudo apt-get update -y
sudo apt-get install -y libasio-dev

mkdir build && cd build

cmake -DENABLE_CPP11=TRUE -DBUILD_EXAMPLES=TRUE -DBUILD_TESTS=TRUE ..

make

make install

-- run test code

cd tutorials/utility_server

g++ -std=c++11 step2.cpp -lboost_system -D_WEBSOCKETPP_CPP11_STL_ -I../../. -lpthread

./a.out

cd tutorials/utility_client

g++ -std=c++11 step6.cpp -lboost_system -D_WEBSOCKETPP_CPP11_STL_ -I../../. -lpthread

./a.out

(note: -I../../. to point to websocketpp directory)

from client (a.out), send connection:

Enter Command: connect ws://localhost:9002

check return ID(i.e 0), send message to server

Enter Command: send 0 hello

tutorial:

https://github.com/taikt/websocketpp/blob/master/tutorials/utility_client/utility_client.md

https://github.com/taikt/websocketpp/blob/master/tutorials/utility_server/utility_server.md



Author
======
Peter Thorson - websocketpp@zaphoyd.com

.. _api:

APIs
=======================

This document is meant to introduce the APIs AppScale provides, including Google App Engine APIs and some other APIs.

Google App Engine APIs
------------------------------------

Foremost, AppScale provides implementations for the Google App Engine APIs. These APIs provide several scalable services which can be leveraged by a Google App Engine application. The Google App Engine APIs are Blobstore, Channel, Datastore, Images, Memcache, Namespaces, TaskQueue, Users, URL Fetch, and XMPP. Google App Engine provides an overview of the APIs and their functionality at http://code.google.com/appengine/docs/. AppScale emulates this functionality using open source software systems, tools, and services, as well as new components.

``Blobstore API``

``Channel API``

``Datastore API``

``Images API``

``Memcache API``

``Namespace API``

``Task Queue API``

``Users API``

``URL Fetch API``

``XMPP API``

MapReduce Streaming APIs
---------------------------

Through Hadoop Streaming, users can specify a Mapper and Reducer pro- gram that can run under the MapReduce programming paradigm. Fault-tolerance and data replication is automatically handled by the Hadoop Streaming framework, and AppScale exposes a simple API that interfaces to Hadoop Stream- ing. This API is:

* ``putMRInput(data, inputLoc)``: Given a string ”data” and a Hadoop file system location “inputLoc”, creates a file on the Hadoop file system named “inputLoc”

EC2 APIs
--------------

AppScale provides an Amazon EC2 API. Users can use this API to spawn virtual machines and manage them entirely through an AppScale web service. The main functions this API provides mirror those of the EC2 command line tools:

* ``ec2_run instances(options)``: Spawns virtual machines with the specified options (interpreted as command-line arguments).

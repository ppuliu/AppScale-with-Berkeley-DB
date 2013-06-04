.. _api:

APIs
=======================

This document is meant to introduce the APIs AppScale provides, including Google App Engine APIs and some other APIs.

Google App Engine APIs
------------------------------------

Foremost, AppScale provides implementations for the Google App Engine APIs. These APIs provide several scalable services which can be leveraged by a Google App Engine application. The Google App Engine APIs are Blobstore, Channel, Datastore, Images, Memcache, Namespaces, TaskQueue, Users, URL Fetch, and XMPP. Google App Engine provides an overview of the APIs and their functionality at http://code.google.com/appengine/docs/. AppScale emulates this functionality using open source software systems, tools, and services, as well as new components.

``Blobstore API``The Blobstore API enables users to store large entities of text or binary data. 

``Channel API``The Channel API allows applications to push messages from the application server to a client’s browser.

``Datastore API``The Datastore API allows for the persistence of data.

``Images API``The Images API facilitates programmatic manipulation of images. 

``Memcache API``The Memcache API permits applications to store their frequently used data in a distributed memory grid. 

``Namespace API``The Namespace API implements the ability to segregate data into different namespaces. 

``Task Queue API``The Google App Engine platform lacks the ability to do threading or computations within a request greater than 30 seconds. 

``Users API``The Users API provides authentication for web applications through the use of cookies.

``URL Fetch API``The URL Fetch API enables an application the ability to do POST and GET requests on remote resources.

``XMPP API``The XMPP API presents the ability to receive and send messages to users with a valid XMPP account. 

MapReduce Streaming APIs
---------------------------

Through Hadoop Streaming, users can specify a Mapper and Reducer pro- gram that can run under the MapReduce programming paradigm. Fault-tolerance and data replication is automatically handled by the Hadoop Streaming framework, and AppScale exposes a simple API that interfaces to Hadoop Stream- ing. This API is:

* ``putMRInput(data, inputLoc)``: Given a string ”data” and a Hadoop file system location “inputLoc”, creates a file on the Hadoop file system named “inputLoc”* ``runMRJob(mapper, reducer, inputLoc, outputLoc, config)``: Given the relative paths to a mapper and reducer file (relative to the main Python file being run), run a Hadoop MapReduce Streaming job. Input is fed to the program via the HDFS file named “inputLoc”, and output is fed to the HDFS file named “outputLoc”. If a hash is passed as ”config”, the key / value pairs are passed as configuration options to Hadoop Streaming.* ``getMROutput(outputLoc)``: Given a Hadoop file system location “outputLoc”, returns a string with the contents of the named file.* ``writeTempFile(suffix, data)``: Writes a file to /tmp on the local machine with the contents data. Is useful for passing a file with nodes to exclude from MapReduce jobs.* ``getAllIPs()``: Returns an array of all the IPs in the AppScale cloud. Is useful for excluding or including nodes based on some user-defined application logic.* ``getNumOfNodes()``: Returns an integer with the number of nodes in the AppScale cloud. Is useful for deter- mining at MapReduce run time, how many Map tasks and Reduce tasks should be run for optimal performance (recommended value is 1 Map task per node).* ``getMRLogs(outputLoc)``: Returns a string with the MapReduce job log for the job whose output is located at outputLoc. Data is returned as a combination of XML and key / value pairs, in the standard Hadoop format.

EC2 APIs
--------------

AppScale provides an Amazon EC2 API. Users can use this API to spawn virtual machines and manage them entirely through an AppScale web service. The main functions this API provides mirror those of the EC2 command line tools:

* ``ec2_run instances(options)``: Spawns virtual machines with the specified options (interpreted as command-line arguments).* ``ec2_describe instances()``: Returns the status of all machines owned by the current user.* ``ec2_terminate instances(options)``: Terminates virtual machines with the specified options (interpreted as command-line arguments).* ``ec2_add keypair(options)``: Creates a new SSH key-pair that can be used to log in to virtual machines that are spawned with this key-pair’s name.* ``ec2_elete keypair(options)``: Deletes the named SSH key-pair from the underlying cloud infrastructure.* ``ec2_describe availability zones(options)``: In Eucalyptus, this returns information relating to the number of vir-tual machines available to be spawned by users.* ``ec2_describe images()``: Returns information about the virtual machine images, ramdisks, and kernels that are available for use in the system.* ``ec2_reboot instances(options)``: Reboots virtual machines with the specified options (interpreted as command- line arguments).


.. _use:

How to use AppScale?
=======================

This document shows how to use AppScale tools to deploy, remove and stop an instance on AppScale.

Deploying Apps to AppScale
------------------------------------

Once you've got AppScale started, you can deploy Google App Engine applications to it. ::

	appscale deploy ~/path-to-your-app

Removing Apps from AppScale
---------------------------

Once you decide you no longer want to have AppScale host an application, you can run "appscale remove appname" to remove that app (presuming that your app was called "appname"). ::

	appscale remove guestbook

Seeing How AppScale is Doing
--------------

You can also use the AppScale Tools to query the status of your AppScale deployment, by running "appscale status". ::

	appscale status

Logging into Your AppScale VMs
-----------------

AppScale runs over Ubuntu Lucid virtual machines. Should you need to log into the machines for any reason, you can run "appscale ssh integer" to log into the machine with id "integer" as root. Since "appscale ssh 0" is the most common machine to log into, you can also use "appscale ssh" as shorthand for "appscale ssh 0". ::

	appscale ssh

Stopping AppScale
-------------------

Once you're done running AppScale and you want to tear it down, run "appscale down". If running in a cloud deployment, this terminates the machines that "appscale up" created, but if running in a cluster deployment, this stops all the API services we started when we ran "appscale up". ::

	appscale down


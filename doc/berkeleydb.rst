.. _berkeleydb:

How to use Berkeley DB in AppScale?
=======================

This document is meant to briefly introduce how to use AppScale with Berkeley DB as the datastore database. There are mainly two steps.

Reinstall AppScale and AppScale Tools
------------------------------------

In order to make AppScale run with Berkeley DB, you need to reinstall AppScale and AppScale Tools using our modified version. In order to install AppScale: ::

	cd /root/appscale/debian/
	bash appscale_build.sh

In order to install AppScale Tools: ::
	
	cd /root/appscale-tools/
	bash appscale_build.sh


Change the configuration file
---------------------------

In order to let AppScale know that you want to use Berkeley DB as the database, you need to modify the configuration file ``AppScalefile``. Find ``table : 'cassandra'`` and change it to ::

	table : 'berkeleydb'

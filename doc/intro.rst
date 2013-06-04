.. _intro:

Introduction
=======================

This document is meant to briefly introduce AppScale, give a look at what AppScale is and why we want to use it.


What is Google App Engine? 
------------------------------------

Google App Engine lets you run web applications on Google's infrastructure. App Engine applications are easy to build, easy to maintain, and easy to scale as your traffic and data storage needs grow. With App Engine, there are no servers to maintain: You just upload your application, and it's ready to serve your users.

You can serve your app from your own domain name (such as http://www.example.com/) using `Google Apps <http://www.google.com/a/>`_. Or, you can serve your app using a free name on the appspot.com domain. You can share your application with the world, or limit access to members of your organization.

Google App Engine supports apps written in several programming languages. With App Engine's Java runtime environment, you can build your app using standard Java technologies, including the JVM, Java servlets, and the Java programming language—or any other language using a JVM-based interpreter or compiler, such as JavaScript or Ruby. App Engine also features two dedicated Python runtime environments, each of which includes a fast Python interpreter and the Python standard library. Finally, App Engine provides a Go runtime environment that runs natively compiled Go code. These runtime environments are built to ensure that your application runs quickly, securely, and without interference from other apps on the system.

With App Engine, you only pay for what you use. There are no set-up costs and no recurring fees. The resources your application uses, such as storage and bandwidth, are measured by the gigabyte, and billed at competitive rates. You control the maximum amounts of resources your app can consume, so it always stays within your budget.

App Engine costs nothing to get started. All applications can use up to 1 GB of storage and enough CPU and bandwidth to support an efficient app serving around 5 million page views a month, absolutely free. When you enable billing for your application, your free limits are raised, and you only pay for resources you use above the free levels.


What is AppScale?
---------------------------

AppScale implements Google's Cloud Platform, App Engine, in open source. In addition to executing your scalable web apps and mobile endpoints on Google's resources, AppScale lets you execute them everywhere else -- on your laptop, behind your firewall, on your datacenter, or on your favorite public or private cloud infrastructure. AppScale is free and easy to use and thus brings Google's "best practices" to devs, giving them the ability to focus on their innovation and MVP without lock-in. 

The AppScale code base, written primarily in the Python programming language, provides the glue code that links these technologies together dynamically with the apps that use them. AppScale automatically configures, deploys, and scales this software across a distributed system. 

When AppScale is deployed, the AppScale tools automatically assign one or more roles to each deployed VM instance. Using this deployment model, AppScale is able to provide fault tolerance and elasticity automatically and in a straightforward manner, since any VM can take on any role on-demand.


Why AppScale?
--------------

The set of features that AppScale brings developers and that sets AppScale apart include: 

* Only production-ready platform with full Google App Engine compatibility
* Unlocked deployment options – execute on your favorite public/private cloud system
* Easy installation and use
* The sweet spot between NoOps and DevOps: convenience vs flexibility and control
* Customer choice of services for API plug-ins
* Automatic configuration, deployment, and scaling and fault tolerance of apps and their   service ecosystems
* Portable and hybrid app deployment across clouds and services
* Uniformity across development, test, and production deployments
* Open, free, customizable execution environment for web apps, services, and mobile backends
* AppScale products for programmer productivity, code/data backup, disaster recovery and more

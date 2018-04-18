Application Archetypes
======================

An application archetype is a model of a workflow application. An instance of an application based on an archetype is ready to be executed, adapted to the User needs

Using archetypes
++++++++++++++++


Prerequisites
*************



Procedure
*********

To generate an application based on an archetype:

* Log on your Developer Cloud Sandbox instance, and type:

.. code-block:: console

  cd
  mvn archetype:generate

* Select the entry relative to the application archetype you want to use.
Currently, archetypes are available for: Python, Bash, R. (---upcoming OTB, SNAP)

In this example, the option 2 (Bash) is selected:

.. code-block:: console

  Choose archetype:
  1: -> com.terradue.ciop.app:dcs-python-archetype (Archetype for Developer Cloud Sandbox Python Applications)
  2: -> com.terradue.ciop.app:dcs-bash-archetype (Archetype for Developer Cloud Sandbox Bash Applications)
  Choose a number or apply filter (format: [groupId:]artifactId, case sensitive contains): : 2

* Set the 'groupId', 'artifactId', 'version' and 'package' values for your project. 
For example:

.. code-block:: console

  Define value for property 'groupId': : com.terradue
  Define value for property 'artifactId': : myapp
  Define value for property 'version':  1.0-SNAPSHOT: : 
  Define value for property 'package':  com.terradue: : myapp

NOTE: the 'version' will be set by default to '1.0-SNAPSHOT'.

After that, you will see a folder with the name of the artifactId (here **myapp**).
You can start building your application from this structure, offering you a powerful mean to handle your Application's packaging, sharing, and Cloud deployments.

In that folder, the resulting Maven configuration file 'pom.xml' will have initial tags similar to:

.. code-block:: bash

  <groupId>com.terradue</groupId>
  <artifactId>myapp</artifactId>
  <packaging>pom</packaging>
  <name>dcs-bash</name>
  <description>dcs-bash</description>
  <version>1.0-SNAPSHOT</version>

Learn more

https://maven.apache.org/pom.html#Properties



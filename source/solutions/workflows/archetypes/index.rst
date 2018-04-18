Application Archetypes
======================

An application archetype is a model of a workflow application. An instance of an application based on an archetype is ready to be executed, and to be adapted accordingly to the specific User needs. Such instance offers a powerful mean to automatically handle the application's packaging (see :doc:`Application Packaging <../packaging>`), sharing, and Cloud deployments.

Using archetypes
++++++++++++++++

In order to generate an application based on an archetype, follow the procedure described below.

* Log on your Developer Cloud Sandbox (see :doc:`Getting Started <../start>`) instance, and type:

.. code-block:: console

  cd
  mvn archetype:generate

* Select the entry relative to the application archetype you want to use. Currently, archetypes are available for: Python, Bash, R [#f1]_. In this example, the option 2 (Bash) is selected:

.. code-block:: console

  Choose archetype:
  1: https://repository.terradue.com/artifactory/libs-release-public/archetype-catalog.xml -> com.terradue.app:dcs-bash-archetype (Archetype for Developer Cloud Sandbox Bash Applications - v2)
  2: https://repository.terradue.com/artifactory/libs-release-public/archetype-catalog.xml -> com.terradue.app:dcs-python-archetype (Archetype for Developer Cloud Sandbox Python Applications - v2)
  3: https://repository.terradue.com/artifactory/libs-release-public/archetype-catalog.xml -> com.terradue.app:dcs-R-archetype (Archetype for Developer Cloud Sandbox R Applications - BETA)
  Choose a number or apply filter (format: [groupId:]artifactId, case sensitive contains): : 2

* Set the 'groupId', 'artifactId', 'version' and 'package' values for your project. For example:

.. code-block:: console

  Define value for property 'groupId': : com.terradue
  Define value for property 'artifactId': : <app-name>
  Define value for property 'version':  1.0-SNAPSHOT: :
  Define value for property 'package':  : : <app-name>
  Define value for property 'community': : <your community, for example geohazards-tep>
  Define value for property 'description': : <a long description of your Application>
  Define value for property 'summary': : <a short description of your Application>

*NOTE*: the 'version' will be set by default to '1.0-SNAPSHOT'.

After that, you will see a folder with the name of the artifactId (here *myapp*), where you can start writing your application, in particular editing the files under:

.. code-block:: console

  ./myapp/src/main/app-resources


.. [#f1] We will provide soon application archetypes for popular software for the Earth Observation, such as `SNAP <http://step.esa.int/main/toolboxes/snap/>`_ and `OTB <https://www.orfeo-toolbox.org/>`_.


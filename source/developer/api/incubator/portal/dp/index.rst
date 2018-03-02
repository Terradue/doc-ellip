Data Packages
=============

Definition
----------

A Data Package is by definition a list of catalogue URLs.
It acts as a view over the Collection. Therefore, it can represent a static datasets list or a dynamic set via search query.
This provides a consistent way for partners (e.g. Portal developers) and users to consistenly use EO data referenced on Terradue catalogue.

A Data Package is queried via an opensearch interface .

Implement your Data Packages
----------------------------

Authentication
~~~~~~~~~~~~~~

We suggest to link User account and data packages by an API key, managed for each registered user at the Portal level.
API Key can be used to retrieve the list of accessible data packages without being logged.

Example:

.. code-block:: url

	https://<your-portal>/data/package/search?key=MY_API_KEY

Implementation
~~~~~~~~~~~~~~

The best practices guidelines to integrate on your portal your own data package implementation is the following:

	- create a database table for datapackages with the following attributes:
		- **unique identifier**
		- **title**
		- **description** (?)
		- **owner id**

	- create a database table for catalogue links with the following attributes:
		- **datapackage identifier**
		- **url**

API
~~~

The following REST services should be available from the portal to access the data packages:

		- GET **/data/package/description** -- returns the opensearch description for data packages search request
		- GET **/data/package/search** -- opensearch request on data packages (should return an AtomFeed with the list of all data packages corresponding to the search parameters)
		- GET **/data/package/<identifier>/description** -- returns the opensearch description for a given data package search request
		- GET **/data/package/<identifier>/search** -- opensearch request on a given data package (should return an AtomFeed with the list of all entries of this data package)		
		- POST **/data/package** -- create a new data package
		- PUT **/data/package** -- update an existing data package
		- DELETE **/data/package/<identifier>** -- delete an existing data package
		- PUT **/data/package/<identifier>/items** -- update list of urls of an existing data package

Use Ellip Data Packages solution
--------------------------------

Authentication
~~~~~~~~~~~~~~

User account and data packages are linked by an API key, managed for each Terradue user at the Portal level.
Your API Key can be used to retrieve the list of your data packages without being logged.

Example:

.. code-block:: url
	
	https://ellip.terradue.com/t2api/data/package/search?key=MY_API_KEY

API
~~~

The following REST services are available for a Ellip user:

	- GET **/data/package/description** -- returns the opensearch description for data packages search request
	- GET **/data/package/search** -- opensearch request on data packages (returns an AtomFeed with the list of all data packages corresponding to the search parameters, available for the authenticated user)
	- GET **/data/package/<identifier>/description** -- returns the opensearch description for a given data package search request
	- GET **/data/package/<identifier>/search** -- opensearch request on a given data package (returns an AtomFeed with the list of all entries of this data package)	
	- POST **/data/package** -- create a new data package
	- PUT **/data/package** -- update an existing data package
	- DELETE **/data/package/<identifier>** -- delete an existing data package
	- PUT **/data/package/<identifier>/items** -- update list of urls of an existing data package

The following REST services are not yet available but are under implemetation:

	- PUT **/data/package/<identifier>/share** -- share an existing data package to a list of Ellip users

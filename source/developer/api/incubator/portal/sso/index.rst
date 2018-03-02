SSO
===

Integrate your OpenID provider with Terradue SSO
------------------------------------------------

Terradue SSO is using OpenID protocol. If you wish to integrate your OpenID provider with Terradue SSO, you just have to follow these steps:

- create on your provider an external **client ID**
- provider us with the **client ID** and **client secret**
- provide us with the Authorization endpoint (e.g GET https://<your-openid-server>/oauth2/authorize)
- provide us with the Token endpoint (e.g GET https://<your-openid-server>/oauth2/token)
- provide us with the Authorization endpoint (e.g GET https://<your-openid-server>/oauth2/userinfo)

The workflow will then be the following:

1/ On T2 portal, user click on “login with <your name>” button
2/ User is redirected to your OpenID server authorization endpoint 

Example:

.. code-block:: url
	
	GET https://<your-openid-server>/oauth2/authorize?response_type=code&scope=<scopes>&client_id=<clientId>&state=<state>&redirect_uri=<t2-redirect_uri>&nonce=<nonce>

3/ User login with his credentials
4/ User is redirected to T2 portal, code and scopes are provided in the url
5/ T2 portal get tokens from code 

Example:

.. code-block:: url
	
	POST https://<your-openid-server>/oauth2/token?grant_type=authorization_code&redirect_uri=<t2-callback-uri>&code=<code>

6/ T2 portal get user info from user info endpoint 

Example:

.. code-block:: url
	
	POST https://<your-openid-server>/oauth2/userinfo?schema=openid?client_id=<clientId>&client_secret=<clientSecret>&grant_type=refresh_token&refresh_token=<token>&scope=<scopes>

7/ User is logged in on Terradue

.. NOTE::
	standard Oauth2 / OpenID endpoints are defined here: `https://connect2id.com/products/server/docs/api <https://connect2id.com/products/server/docs/api>`_
# Class: Signet::OAuth2::Client #
<dl>
<blockquote><dt>Inherits:</dt>
<dd>Object > Signet::OAuth2::Client</dd>
<dt>Defined in:</dt>
<dd><code>lib/signet/oauth_2/client.rb</code></dd>
</dl>
<h2>Constructor Details</h2>
<h3>Method: <code>Signet::OAuth2::Client#initialize</code></h3>
(Client)  <b><code>initialize</code></b> <code>(options = {})</code> — Creates an OAuth 2.0 client.<br>
<h4>Examples</h4>
<h5></h5>
<pre><code>client = Signet::OAuth2::Client.new(<br>
  :authorization_endpoint_uri =&gt;<br>
    'https://example.server.com/authorization',<br>
  :token_endpoint_uri =&gt;<br>
    'https://example.server.com/token',<br>
  :client_id =&gt; 'anonymous',<br>
  :client_secret =&gt; 'anonymous',<br>
  :scope =&gt; 'example',<br>
  :redirect_uri =&gt; 'https://example.client.com/oauth'<br>
)<br>
</code></pre>
<h4>Parameters</h4>
(Hash) <b><code>options</code></b> <i>(defaults to: <code>{}</code>)</i> — The configuration parameters for the client.<br>
- <code>:authorization_uri</code> —<br>
The authorization server's HTTP endpoint capable of<br>
authenticating the end-user and obtaining authorization.<br>
- <code>:token_credential_uri</code> —<br>
The authorization server's HTTP endpoint capable of issuing<br>
tokens and refreshing expired tokens.<br>
- <code>:client_id</code> —<br>
A unique identifier issued to the client to identify itself to the<br>
authorization server.<br>
- <code>:client_secret</code> —<br>
A shared symmetric secret issued by the authorization server,<br>
which is used to authenticate the client.<br>
- <code>:scope</code> —<br>
The scope of the access request, expressed either as an Array<br>
or as a space-delimited String.<br>
- <code>:state</code> —<br>
An arbitrary string designed to allow the client to maintain state.<br>
- <code>:code</code> —<br>
The authorization code received from the authorization server.<br>
- <code>:redirect_uri</code> —<br>
The redirection URI used in the initial request.<br>
- <code>:username</code> —<br>
The resource owner's username.<br>
- <code>:password</code> —<br>
The resource owner's password.<br>
- <code>:refresh_token</code> —<br>
The refresh token associated with the access token<br>
to be refreshed.<br>
- <code>:access_token</code> —<br>
The current access token for this client.<br>
- <code>:id_token</code> —<br>
The current ID token for this client.<br>
- <code>:extension_parameters</code> —<br>
When using an extension grant type, this the set of parameters used<br>
by that extension.<br />
<h4>See Also</h4>
<a href='#Method%3A_Signet%3A%3AOAuth2%3A%3AClient%23update%21.md'>#update!</a><br />
<hr />
<h2>Instance Method Details</h2>
<h3>Method: <code>Signet::OAuth2::Client#access_token</code></h3>
(String)  <b><code>access_token</code></b> — Returns the access token associated with this client.<br>
<h4>Returns</h4>
(String) — The access token.<br />
<h3>Method: <code>Signet::OAuth2::Client#access_token=</code></h3>
(Object)  <b><code>access_token=</code></b> <code>(new_access_token)</code> — Sets the access token associated with this client.<br>
<h4>Parameters</h4>
(String) <b><code>new_access_token</code></b> — The access token.<br />
<h3>Method: <code>Signet::OAuth2::Client#authorization_uri</code></h3>
(Addressable::URI)  <b><code>authorization_uri</code></b> <code>(options = {})</code> — Returns the authorization URI that the user should be redirected to.<br>
<h4>Returns</h4>
(Addressable::URI) — The authorization URI.<br />
<h4>See Also</h4>
<a href='SignetOAuth2#Method%3A_Signet%3A%3AOAuth2.generate_authorization_uri.md'>Signet::OAuth2.generate_authorization_uri</a><br />
<h3>Method: <code>Signet::OAuth2::Client#authorization_uri=</code></h3>
(Object)  <b><code>authorization_uri=</code></b> <code>(new_authorization_uri)</code> — Sets the authorization URI for this client.<br>
<h4>Parameters</h4>
(Addressable::URI, String, #to_str) <b><code>new_authorization_uri</code></b> — The authorization URI.<br />
<h3>Method: <code>Signet::OAuth2::Client#client_id</code></h3>
(String)  <b><code>client_id</code></b> — Returns the client identifier for this client.<br>
<h4>Returns</h4>
(String) — The client identifier.<br />
<h3>Method: <code>Signet::OAuth2::Client#client_id=</code></h3>
(Object)  <b><code>client_id=</code></b> <code>(new_client_id)</code> — Sets the client identifier for this client.<br>
<h4>Parameters</h4>
(String) <b><code>new_client_id</code></b> — The client identifier.<br />
<h3>Method: <code>Signet::OAuth2::Client#client_secret</code></h3>
(String)  <b><code>client_secret</code></b> — Returns the client secret for this client.<br>
<h4>Returns</h4>
(String) — The client secret.<br />
<h3>Method: <code>Signet::OAuth2::Client#client_secret=</code></h3>
(Object)  <b><code>client_secret=</code></b> <code>(new_client_secret)</code> — Sets the client secret for this client.<br>
<h4>Parameters</h4>
(String) <b><code>new_client_secret</code></b> — The client secret.<br />
<h3>Method: <code>Signet::OAuth2::Client#code</code></h3>
(String)  <b><code>code</code></b> — Returns the authorization code issued to this client.<br>
Used only by the authorization code access grant type.<br>
<h4>Returns</h4>
(String) — The authorization code.<br />
<h3>Method: <code>Signet::OAuth2::Client#code=</code></h3>
(Object)  <b><code>code=</code></b> <code>(new_code)</code> — Sets the authorization code issued to this client.<br>
Used only by the authorization code access grant type.<br>
<h4>Parameters</h4>
(String) <b><code>new_code</code></b> — The authorization code.<br />
<h3>Method: <code>Signet::OAuth2::Client#decoded_id_token</code></h3>
(String)  <b><code>decoded_id_token</code></b> <code>(public_key = nil)</code> — Returns the decoded ID token associated with this client.<br>
<h4>Parameters</h4>
(OpenSSL::PKey::RSA, Object) <b><code>public_key</code></b> <i>(defaults to: <code>nil</code>)</i> — The public key to use to verify the ID token. Skips verification if<br>
omitted.<br />
<h4>Returns</h4>
(String) — The decoded ID token.<br />
<h3>Method: <code>Signet::OAuth2::Client#expired?</code></h3>
(TrueClass, FalseClass)  <b><code>expired?</code></b> — Returns true if the access token has expired.<br>
<h4>Returns</h4>
(TrueClass, FalseClass) — The expiration state of the access token.<br />
<h3>Method: <code>Signet::OAuth2::Client#expires_at</code></h3>
(Integer)  <b><code>expires_at</code></b> — Returns the timestamp the access token will expire at.<br>
<h4>Returns</h4>
(Integer) — The access token lifetime.<br />
<h3>Method: <code>Signet::OAuth2::Client#expires_in</code></h3>
(Integer)  <b><code>expires_in</code></b> — Returns the lifetime of the access token in seconds.<br>
<h4>Returns</h4>
(Integer) — The access token lifetime.<br />
<h3>Method: <code>Signet::OAuth2::Client#expires_in=</code></h3>
(Object)  <b><code>expires_in=</code></b> <code>(new_expires_in)</code> — Sets the lifetime of the access token in seconds.  Resets the issued<br>
timestamp.<br>
<h4>Parameters</h4>
(String) <b><code>new_expires_in</code></b> — The access token lifetime.<br />
<h3>Method: <code>Signet::OAuth2::Client#extension_parameters</code></h3>
(Hash)  <b><code>extension_parameters</code></b> — Returns the set of extension parameters used by the client.<br>
Used only by extension access grant types.<br>
<h4>Returns</h4>
(Hash) — The extension parameters.<br />
<h3>Method: <code>Signet::OAuth2::Client#extension_parameters=</code></h3>
(Object)  <b><code>extension_parameters=</code></b> <code>(new_extension_parameters)</code> — Sets extension parameters used by the client.<br>
Used only by extension access grant types.<br>
<h4>Parameters</h4>
(Hash) <b><code>new_extension_parameters</code></b> — The parameters.<br />
<h3>Method: <code>Signet::OAuth2::Client#fetch_access_token</code></h3>
(Object)  <b><code>fetch_access_token</code></b> <code>(options = {})</code> —<br>
<h3>Method: <code>Signet::OAuth2::Client#fetch_access_token!</code></h3>
(Object)  <b><code>fetch_access_token!</code></b> <code>(options = {})</code> —<br>
<h3>Method: <code>Signet::OAuth2::Client#fetch_protected_resource</code></h3>
(Array)  <b><code>fetch_protected_resource</code></b> <code>(options = {})</code> — Transmits a request for a protected resource.<br>
<h4>Examples</h4>
<h5></h5>
<pre><code># Using Net::HTTP<br>
response = client.fetch_protected_resource(<br>
  :uri =&gt; 'http://www.example.com/protected/resource'<br>
)<br>
</code></pre>
<h5></h5>
<pre><code># Using Typhoeus<br>
response = client.fetch_protected_resource(<br>
  :request =&gt; Typhoeus::Request.new(<br>
    'http://www.example.com/protected/resource'<br>
  ),<br>
  :adapter =&gt; HTTPAdapter::TyphoeusAdapter.new,<br>
  :connection =&gt; connection<br>
)<br>
</code></pre>
<h4>Parameters</h4>
(Hash) <b><code>options</code></b> <i>(defaults to: <code>{}</code>)</i> — The configuration parameters for the request.<br>
- <code>:request</code> —<br>
A pre-constructed request.  An OAuth 2 Authorization header<br>
will be added to it, as well as an explicit Cache-Control<br>
<code>no-store</code> directive.<br>
- <code>:method</code> —<br>
The HTTP method for the request.  Defaults to 'GET'.<br>
- <code>:uri</code> —<br>
The URI for the request.<br>
- <code>:headers</code> —<br>
The HTTP headers for the request.<br>
- <code>:body</code> —<br>
The HTTP body for the request.<br>
- <code>:realm</code> —<br>
The Authorization realm.  See RFC 2617.<br>
- <code>:connection</code> —<br>
The HTTP connection to use.<br>
Must be of type <code>Faraday::Connection</code>.<br />
<h4>Returns</h4>
(Array) — The response object.<br />
<h3>Method: <code>Signet::OAuth2::Client#generate_access_token_request</code></h3>
(Array)  <b><code>generate_access_token_request</code></b> <code>(options = {})</code> — Generates a request for token credentials.<br>
<h4>Parameters</h4>
(Hash) <b><code>options</code></b> <i>(defaults to: <code>{}</code>)</i> — The configuration parameters for the request.<br>
- <code>:code</code> —<br>
The authorization code.<br />
<h4>Returns</h4>
(Array) — The request object.<br />
<h3>Method: <code>Signet::OAuth2::Client#generate_authenticated_request</code></h3>
(Array)  <b><code>generate_authenticated_request</code></b> <code>(options = {})</code> — Generates an authenticated request for protected resources.<br>
<h4>Parameters</h4>
(Hash) <b><code>options</code></b> <i>(defaults to: <code>{}</code>)</i> — The configuration parameters for the request.<br>
- <code>:request</code> —<br>
A pre-constructed request.  An OAuth 2 Authorization header<br>
will be added to it, as well as an explicit Cache-Control<br>
<code>no-store</code> directive.<br>
- <code>:method</code> —<br>
The HTTP method for the request.  Defaults to 'GET'.<br>
- <code>:uri</code> —<br>
The URI for the request.<br>
- <code>:headers</code> —<br>
The HTTP headers for the request.<br>
- <code>:body</code> —<br>
The HTTP body for the request.<br>
- <code>:realm</code> —<br>
The Authorization realm.  See RFC 2617.<br />
<h4>Returns</h4>
(Array) — The request object.<br />
<h3>Method: <code>Signet::OAuth2::Client#grant_type</code></h3>
(String)  <b><code>grant_type</code></b> — Returns the inferred grant type, based on the current state of the<br>
client object.  Returns <code>"none"</code> if the client has insufficient<br>
information to make an in-band authorization request.<br>
<h4>Returns</h4>
(String) — The inferred grant type.<br />
<h3>Method: <code>Signet::OAuth2::Client#grant_type=</code></h3>
(Object)  <b><code>grant_type=</code></b> <code>(new_grant_type)</code> —<br>
<h3>Method: <code>Signet::OAuth2::Client#id_token</code></h3>
(String)  <b><code>id_token</code></b> — Returns the ID token associated with this client.<br>
<h4>Returns</h4>
(String) — The ID token.<br />
<h3>Method: <code>Signet::OAuth2::Client#id_token=</code></h3>
(Object)  <b><code>id_token=</code></b> <code>(new_id_token)</code> — Sets the ID token associated with this client.<br>
<h4>Parameters</h4>
(String) <b><code>new_id_token</code></b> — The ID token.<br />
<h3>Method: <code>Signet::OAuth2::Client#issued_at</code></h3>
(Integer)  <b><code>issued_at</code></b> — Returns the timestamp the access token was issued at.<br>
<h4>Returns</h4>
(Integer) — The access token issuance time.<br />
<h3>Method: <code>Signet::OAuth2::Client#issued_at=</code></h3>
(Object)  <b><code>issued_at=</code></b> <code>(new_issued_at)</code> — Sets the timestamp the access token was issued at.<br>
<h4>Parameters</h4>
(String) <b><code>new_issued_at</code></b> — The access token issuance time.<br />
<h3>Method: <code>Signet::OAuth2::Client#password</code></h3>
(String)  <b><code>password</code></b> — Returns the password associated with this client.<br>
Used only by the resource owner password credential access grant type.<br>
<h4>Returns</h4>
(String) — The password.<br />
<h3>Method: <code>Signet::OAuth2::Client#password=</code></h3>
(Object)  <b><code>password=</code></b> <code>(new_password)</code> — Sets the password associated with this client.<br>
Used only by the resource owner password credential access grant type.<br>
<h4>Parameters</h4>
(String) <b><code>new_password</code></b> — The password.<br />
<h3>Method: <code>Signet::OAuth2::Client#redirect_uri</code></h3>
(String)  <b><code>redirect_uri</code></b> — Returns the redirect URI for this client.<br>
<h4>Returns</h4>
(String) — The redirect URI.<br />
<h3>Method: <code>Signet::OAuth2::Client#redirect_uri=</code></h3>
(Object)  <b><code>redirect_uri=</code></b> <code>(new_redirect_uri)</code> — Sets the redirect URI for this client.<br>
<h4>Parameters</h4>
(String) <b><code>new_redirect_uri</code></b> — The redirect URI.<br />
<h3>Method: <code>Signet::OAuth2::Client#refresh_token</code></h3>
(String)  <b><code>refresh_token</code></b> — Returns the refresh token associated with this client.<br>
<h4>Returns</h4>
(String) — The refresh token.<br />
<h3>Method: <code>Signet::OAuth2::Client#refresh_token=</code></h3>
(Object)  <b><code>refresh_token=</code></b> <code>(new_refresh_token)</code> — Sets the refresh token associated with this client.<br>
<h4>Parameters</h4>
(String) <b><code>new_refresh_token</code></b> — The refresh token.<br />
<h3>Method: <code>Signet::OAuth2::Client#scope</code></h3>
(Array)  <b><code>scope</code></b> — Returns the scope for this client.  Scope is a list of access ranges<br>
defined by the authorization server.<br>
<h4>Returns</h4>
(Array) — The scope of access the client is requesting.<br />
<h3>Method: <code>Signet::OAuth2::Client#scope=</code></h3>
(Object)  <b><code>scope=</code></b> <code>(new_scope)</code> — Sets the scope for this client.<br>
<h4>Parameters</h4>
(Array, String) <b><code>new_scope</code></b> — The scope of access the client is requesting.  This may be<br>
expressed as either an Array of String objects or as a<br>
space-delimited String.<br />
<h3>Method: <code>Signet::OAuth2::Client#state</code></h3>
(String)  <b><code>state</code></b> — Returns the client's current state value.<br>
<h4>Returns</h4>
(String) — The state value.<br />
<h3>Method: <code>Signet::OAuth2::Client#state=</code></h3>
(Object)  <b><code>state=</code></b> <code>(new_state)</code> — Sets the client's current state value.<br>
<h4>Parameters</h4>
(String) <b><code>new_state</code></b> — The state value.<br />
<h3>Method: <code>Signet::OAuth2::Client#token_credential_uri</code></h3>
(Addressable::URI)  <b><code>token_credential_uri</code></b> — Returns the token credential URI for this client.<br>
<h4>Returns</h4>
(Addressable::URI) — The token credential URI.<br />
<h3>Method: <code>Signet::OAuth2::Client#token_credential_uri=</code></h3>
(Object)  <b><code>token_credential_uri=</code></b> <code>(new_token_credential_uri)</code> — Sets the token credential URI for this client.<br>
<h4>Parameters</h4>
(Addressable::URI, String, #to_str) <b><code>new_token_credential_uri</code></b> — The token credential URI.<br />
<h3>Method: <code>Signet::OAuth2::Client#update!</code></h3>
(Object)  <b><code>update!</code></b> <code>(options = {})</code> — Updates an OAuth 2.0 client.<br>
<h4>Examples</h4>
<h5></h5>
<pre><code>client.update!(<br>
  :code =&gt; 'i1WsRn1uB1',<br>
  :access_token =&gt; 'FJQbwq9',<br>
  :expires_in =&gt; 3600<br>
)<br>
</code></pre>
<h4>Parameters</h4>
(Hash) <b><code>options</code></b> <i>(defaults to: <code>{}</code>)</i> — The configuration parameters for the client.<br>
- <code>:authorization_uri</code> —<br>
The authorization server's HTTP endpoint capable of<br>
authenticating the end-user and obtaining authorization.<br>
- <code>:token_credential_uri</code> —<br>
The authorization server's HTTP endpoint capable of issuing<br>
tokens and refreshing expired tokens.<br>
- <code>:client_id</code> —<br>
A unique identifier issued to the client to identify itself to the<br>
authorization server.<br>
- <code>:client_secret</code> —<br>
A shared symmetric secret issued by the authorization server,<br>
which is used to authenticate the client.<br>
- <code>:scope</code> —<br>
The scope of the access request, expressed either as an Array<br>
or as a space-delimited String.<br>
- <code>:state</code> —<br>
An arbitrary string designed to allow the client to maintain state.<br>
- <code>:code</code> —<br>
The authorization code received from the authorization server.<br>
- <code>:redirect_uri</code> —<br>
The redirection URI used in the initial request.<br>
- <code>:username</code> —<br>
The resource owner's username.<br>
- <code>:password</code> —<br>
The resource owner's password.<br>
- <code>:refresh_token</code> —<br>
The refresh token associated with the access token<br>
to be refreshed.<br>
- <code>:access_token</code> —<br>
The current access token for this client.<br>
- <code>:id_token</code> —<br>
The current ID token for this client.<br>
- <code>:extension_parameters</code> —<br>
When using an extension grant type, this the set of parameters used<br>
by that extension.<br />
<h4>See Also</h4>
<a href='#Method%3A_Signet%3A%3AOAuth2%3A%3AClient%23initialize.md'>#initialize</a><br />
<a href='#Method%3A_Signet%3A%3AOAuth2%3A%3AClient%23update_token%21.md'>#update_token!</a><br />
<h3>Method: <code>Signet::OAuth2::Client#update_token!</code></h3>
(Object)  <b><code>update_token!</code></b> <code>(options = {})</code> — Updates an OAuth 2.0 client.<br>
<h4>Examples</h4>
<h5></h5>
<pre><code>client.update!(<br>
  :refresh_token =&gt; 'n4E9O119d',<br>
  :access_token =&gt; 'FJQbwq9',<br>
  :expires_in =&gt; 3600<br>
)<br>
</code></pre>
<h4>Parameters</h4>
(Hash) <b><code>options</code></b> <i>(defaults to: <code>{}</code>)</i> — The configuration parameters related to the token.<br>
- <code>:refresh_token</code> —<br>
The refresh token associated with the access token<br>
to be refreshed.<br>
- <code>:access_token</code> —<br>
The current access token for this client.<br>
- <code>:id_token</code> —<br>
The current ID token for this client.<br>
- <code>:expires_in</code> —<br>
The time in seconds until access token expiration.<br>
- <code>:issued_at</code> —<br>
The timestamp that the token was issued at.<br />
<h4>See Also</h4>
<a href='#Method%3A_Signet%3A%3AOAuth2%3A%3AClient%23initialize.md'>#initialize</a><br />
<a href='#Method%3A_Signet%3A%3AOAuth2%3A%3AClient%23update%21.md'>#update!</a><br />
<h3>Method: <code>Signet::OAuth2::Client#username</code></h3>
(String)  <b><code>username</code></b> — Returns the username associated with this client.<br>
Used only by the resource owner password credential access grant type.<br>
<h4>Returns</h4>
(String) — The username.<br />
<h3>Method: <code>Signet::OAuth2::Client#username=</code></h3>
(Object)  <b><code>username=</code></b> <code>(new_username)</code> — Sets the username associated with this client.<br>
Used only by the resource owner password credential access grant type.<br>
<h4>Parameters</h4>
(String) <b><code>new_username</code></b> — The username.<br />
<hr />
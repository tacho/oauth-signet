# Class: Signet::OAuth1::Client #
<dl>
<blockquote><dt>Inherits:</dt>
<dd>Object > Signet::OAuth1::Client</dd>
<dt>Defined in:</dt>
<dd><code>lib/signet/oauth_1/client.rb</code></dd>
</dl>
<h2>Constructor Details</h2>
<h3>Method: <code>Signet::OAuth1::Client#initialize</code></h3>
(Client)  <b><code>initialize</code></b> <code>(options = {})</code> — Creates an OAuth 1.0 client.<br>
<h4>Examples</h4>
<h5></h5>
<pre><code>client = Signet::OAuth1::Client.new(<br>
  :temporary_credential_uri =&gt;<br>
    'https://www.google.com/accounts/OAuthGetRequestToken',<br>
  :authorization_uri =&gt;<br>
    'https://www.google.com/accounts/OAuthAuthorizeToken',<br>
  :token_credential_uri =&gt;<br>
    'https://www.google.com/accounts/OAuthGetAccessToken',<br>
  :client_credential_key =&gt; 'anonymous',<br>
  :client_credential_secret =&gt; 'anonymous'<br>
)<br>
</code></pre>
<h4>Parameters</h4>
(Hash) <b><code>options</code></b> <i>(defaults to: <code>{}</code>)</i> — The configuration parameters for the client.<br>
- <code>:temporary_credential_uri</code> —<br>
The OAuth temporary credentials URI.<br>
- <code>:authorization_uri</code> —<br>
The OAuth authorization URI.<br>
- <code>:token_credential_uri</code> —<br>
The OAuth token credentials URI.<br>
- <code>:client_credential_key</code> —<br>
The OAuth client credential key.<br>
- <code>:client_credential_secret</code> —<br>
The OAuth client credential secret.<br>
- <code>:callback</code> —  The OAuth callback.  Defaults to 'oob'.<br />
<hr />
<h2>Instance Method Details</h2>
<h3>Method: <code>Signet::OAuth1::Client#authorization_uri</code></h3>
(Addressable::URI)  <b><code>authorization_uri</code></b> <code>(options = {})</code> — Returns the authorization URI that the user should be redirected to.<br>
<h4>Returns</h4>
(Addressable::URI) — The authorization URI.<br />
<h4>See Also</h4>
<a href='SignetOAuth1#Method%3A_Signet%3A%3AOAuth1.generate_authorization_uri.md'>Signet::OAuth1.generate_authorization_uri</a><br />
<h3>Method: <code>Signet::OAuth1::Client#authorization_uri=</code></h3>
(Object)  <b><code>authorization_uri=</code></b> <code>(new_authorization_uri)</code> — Sets the authorization URI for this client.<br>
<h4>Parameters</h4>
(Addressable::URI, String, #to_str) <b><code>new_authorization_uri</code></b> — The authorization URI.<br />
<h3>Method: <code>Signet::OAuth1::Client#callback</code></h3>
(String)  <b><code>callback</code></b> — Returns the callback for this client.<br>
<h4>Returns</h4>
(String) — The OAuth callback.<br />
<h3>Method: <code>Signet::OAuth1::Client#callback=</code></h3>
(Object)  <b><code>callback=</code></b> <code>(new_callback)</code> — Sets the callback for this client.<br>
<h4>Parameters</h4>
(String, #to_str) <b><code>new_callback</code></b> — The OAuth callback.<br />
<h3>Method: <code>Signet::OAuth1::Client#client_credential</code></h3>
(<a href='SignetOAuth1Credential.md'>Signet::OAuth1::Credential</a>)  <b><code>client_credential</code></b><i>Also known as:</i> consumer_token — Returns the client credential for this client.<br>
<h4>Returns</h4>
(<a href='SignetOAuth1Credential.md'>Signet::OAuth1::Credential</a>) — The client credentials.<br />
<h3>Method: <code>Signet::OAuth1::Client#client_credential=</code></h3>
(Object)  <b><code>client_credential=</code></b> <code>(new_client_credential)</code><i>Also known as:</i> consumer_token= — Sets the client credential for this client.<br>
<h4>Parameters</h4>
(<a href='SignetOAuth1Credential.md'>Signet::OAuth1::Credential</a>) <b><code>new_client_credential</code></b> — The client credentials.<br />
<h3>Method: <code>Signet::OAuth1::Client#client_credential_key</code></h3>
(String)  <b><code>client_credential_key</code></b><i>Also known as:</i> consumer_key — Returns the client credential key for this client.<br>
<h4>Returns</h4>
(String) — The client credential key.<br />
<h3>Method: <code>Signet::OAuth1::Client#client_credential_key=</code></h3>
(Object)  <b><code>client_credential_key=</code></b> <code>(new_client_credential_key)</code><i>Also known as:</i> consumer_key= — Sets the client credential key for this client.<br>
<h4>Parameters</h4>
(String, #to_str) <b><code>new_client_credential_key</code></b> — The client credential key.<br />
<h3>Method: <code>Signet::OAuth1::Client#client_credential_secret</code></h3>
(String)  <b><code>client_credential_secret</code></b><i>Also known as:</i> consumer_secret — Returns the client credential secret for this client.<br>
<h4>Returns</h4>
(String) — The client credential secret.<br />
<h3>Method: <code>Signet::OAuth1::Client#client_credential_secret=</code></h3>
(Object)  <b><code>client_credential_secret=</code></b> <code>(new_client_credential_secret)</code><i>Also known as:</i> consumer_secret= — Sets the client credential secret for this client.<br>
<h4>Parameters</h4>
(String, #to_str) <b><code>new_client_credential_secret</code></b> — The client credential secret.<br />
<h3>Method: <code>Signet::OAuth1::Client#fetch_protected_resource</code></h3>
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
  :connection =&gt; connection<br>
)<br>
</code></pre>
<h4>Parameters</h4>
(Hash) <b><code>options</code></b> <i>(defaults to: <code>{}</code>)</i> — The configuration parameters for the request.<br>
- <code>:request</code> —<br>
A pre-constructed request to sign.<br>
- <code>:method</code> —<br>
The HTTP method for the request.  Defaults to :get.<br>
- <code>:uri</code> —<br>
The URI for the request.<br>
- <code>:headers</code> —<br>
The HTTP headers for the request.<br>
- <code>:body</code> —<br>
The HTTP body for the request.<br>
- <code>:signature_method</code> —<br>
The signature method.  Defaults to <code>'HMAC-SHA1'</code>.<br>
- <code>:realm</code> —<br>
The Authorization realm.  See RFC 2617.<br>
- <code>:connection</code> —<br>
The HTTP connection to use.<br>
Must be of type <code>Faraday::Connection</code>.<br />
<h4>Returns</h4>
(Array) — The response object.<br />
<h3>Method: <code>Signet::OAuth1::Client#fetch_temporary_credential</code></h3>
(<a href='SignetOAuth1Credential.md'>Signet::OAuth1::Credential</a>)  <b><code>fetch_temporary_credential</code></b> <code>(options = {})</code><i>Also known as:</i> fetch_request_token — Transmits a request for a temporary credential.  This method does not<br>
have side-effects within the client.<br>
<h4>Examples</h4>
<h5></h5>
<pre><code>temporary_credential = client.fetch_temporary_credential(<br>
  :additional_parameters =&gt; {<br>
    :scope =&gt; 'https://mail.google.com/mail/feed/atom'<br>
  }<br>
)<br>
</code></pre>
<h4>Parameters</h4>
(Hash) <b><code>options</code></b> <i>(defaults to: <code>{}</code>)</i> — The configuration parameters for the request.<br>
- <code>:signature_method</code> —<br>
The signature method.  Defaults to <code>'HMAC-SHA1'</code>.<br>
- <code>:additional_parameters</code> —<br>
Non-standard additional parameters.<br>
- <code>:realm</code> —<br>
The Authorization realm.  See RFC 2617.<br>
- <code>:connection</code> —<br>
The HTTP connection to use.<br>
Must be of type <code>Faraday::Connection</code>.<br />
<h4>Returns</h4>
(<a href='SignetOAuth1Credential.md'>Signet::OAuth1::Credential</a>) — The temporary credential.<br />
<h3>Method: <code>Signet::OAuth1::Client#fetch_temporary_credential!</code></h3>
(<a href='SignetOAuth1Credential.md'>Signet::OAuth1::Credential</a>)  <b><code>fetch_temporary_credential!</code></b> <code>(options = {})</code><i>Also known as:</i> fetch_request_token! — Transmits a request for a temporary credential.  This method updates<br>
the client with the new temporary credential.<br>
<h4>Examples</h4>
<h5></h5>
<pre><code>client.fetch_temporary_credential!(:additional_parameters =&gt; {<br>
  :scope =&gt; 'https://mail.google.com/mail/feed/atom'<br>
})<br>
</code></pre>
<h4>Parameters</h4>
(Hash) <b><code>options</code></b> <i>(defaults to: <code>{}</code>)</i> — The configuration parameters for the request.<br>
- <code>:signature_method</code> —<br>
The signature method.  Defaults to <code>'HMAC-SHA1'</code>.<br>
- <code>:additional_parameters</code> —<br>
Non-standard additional parameters.<br>
- <code>:realm</code> —<br>
The Authorization realm.  See RFC 2617.<br>
- <code>:connection</code> —<br>
The HTTP connection to use.<br>
Must be of type <code>Faraday::Connection</code>.<br />
<h4>Returns</h4>
(<a href='SignetOAuth1Credential.md'>Signet::OAuth1::Credential</a>) — The temporary credential.<br />
<h3>Method: <code>Signet::OAuth1::Client#fetch_token_credential</code></h3>
(<a href='SignetOAuth1Credential.md'>Signet::OAuth1::Credential</a>)  <b><code>fetch_token_credential</code></b> <code>(options = {})</code><i>Also known as:</i> fetch_access_token — Transmits a request for a token credential.  This method does not<br>
have side-effects within the client.<br>
<h4>Examples</h4>
<h5></h5>
<pre><code>token_credential = client.fetch_token_credential(<br>
  :verifier =&gt; '12345'<br>
)<br>
</code></pre>
<h4>Parameters</h4>
(Hash) <b><code>options</code></b> <i>(defaults to: <code>{}</code>)</i> — The configuration parameters for the request.<br>
- <code>:verifier</code> —<br>
The OAuth verifier provided by the server.  Required.<br>
- <code>:signature_method</code> —<br>
The signature method.  Defaults to <code>'HMAC-SHA1'</code>.<br>
- <code>:realm</code> —<br>
The Authorization realm.  See RFC 2617.<br>
- <code>:connection</code> —<br>
The HTTP connection to use.<br>
Must be of type <code>Faraday::Connection</code>.<br />
<h4>Returns</h4>
(<a href='SignetOAuth1Credential.md'>Signet::OAuth1::Credential</a>) — The token credential.<br />
<h3>Method: <code>Signet::OAuth1::Client#fetch_token_credential!</code></h3>
(<a href='SignetOAuth1Credential.md'>Signet::OAuth1::Credential</a>)  <b><code>fetch_token_credential!</code></b> <code>(options = {})</code><i>Also known as:</i> fetch_access_token! — Transmits a request for a token credential.  This method updates<br>
the client with the new token credential.<br>
<h4>Examples</h4>
<h5></h5>
<pre><code>client.fetch_token_credential!(:verifier =&gt; '12345')<br>
</code></pre>
<h4>Parameters</h4>
(Hash) <b><code>options</code></b> <i>(defaults to: <code>{}</code>)</i> — The configuration parameters for the request.<br>
- <code>:signature_method</code> —<br>
The signature method.  Defaults to <code>'HMAC-SHA1'</code>.<br>
- <code>:additional_parameters</code> —<br>
Non-standard additional parameters.<br>
- <code>:realm</code> —<br>
The Authorization realm.  See RFC 2617.<br>
- <code>:connection</code> —<br>
The HTTP connection to use.<br>
Must be of type <code>Faraday::Connection</code>.<br />
<h4>Returns</h4>
(<a href='SignetOAuth1Credential.md'>Signet::OAuth1::Credential</a>) — The token credential.<br />
<h3>Method: <code>Signet::OAuth1::Client#generate_authenticated_request</code></h3>
(Array)  <b><code>generate_authenticated_request</code></b> <code>(options = {})</code> — Generates an authenticated request for protected resources.<br>
<h4>Parameters</h4>
(Hash) <b><code>options</code></b> <i>(defaults to: <code>{}</code>)</i> — The configuration parameters for the request.<br>
- <code>:request</code> —<br>
A pre-constructed request to sign.<br>
- <code>:method</code> —<br>
The HTTP method for the request.  Defaults to :get.<br>
- <code>:uri</code> —<br>
The URI for the request.<br>
- <code>:headers</code> —<br>
The HTTP headers for the request.<br>
- <code>:body</code> —<br>
The HTTP body for the request.<br>
- <code>:signature_method</code> —<br>
The signature method.  Defaults to <code>'HMAC-SHA1'</code>.<br>
- <code>:realm</code> —<br>
The Authorization realm.  See RFC 2617.<br />
<h4>Returns</h4>
(Array) — The request object.<br />
<h3>Method: <code>Signet::OAuth1::Client#generate_temporary_credential_request</code></h3>
(Array)  <b><code>generate_temporary_credential_request</code></b> <code>(options = {})</code><i>Also known as:</i> generate_request_token_request — Generates a request for temporary credentials.<br>
<h4>Parameters</h4>
(Hash) <b><code>options</code></b> <i>(defaults to: <code>{}</code>)</i> — The configuration parameters for the request.<br>
- <code>:signature_method</code> —<br>
The signature method.  Defaults to <code>'HMAC-SHA1'</code>.<br>
- <code>:additional_parameters</code> —<br>
Non-standard additional parameters.<br>
- <code>:realm</code> —<br>
The Authorization realm.  See RFC 2617.<br />
<h4>Returns</h4>
(Array) — The request object.<br />
<h3>Method: <code>Signet::OAuth1::Client#generate_token_credential_request</code></h3>
(Array)  <b><code>generate_token_credential_request</code></b> <code>(options = {})</code><i>Also known as:</i> generate_access_token_request — Generates a request for token credentials.<br>
<h4>Parameters</h4>
(Hash) <b><code>options</code></b> <i>(defaults to: <code>{}</code>)</i> — The configuration parameters for the request.<br>
- <code>:verifier</code> —<br>
The OAuth verifier provided by the server.  Required.<br>
- <code>:signature_method</code> —<br>
The signature method.  Defaults to <code>'HMAC-SHA1'</code>.<br>
- <code>:realm</code> —<br>
The Authorization realm.  See RFC 2617.<br />
<h4>Returns</h4>
(Array) — The request object.<br />
<h3>Method: <code>Signet::OAuth1::Client#temporary_credential</code></h3>
(<a href='SignetOAuth1Credential.md'>Signet::OAuth1::Credential</a>)  <b><code>temporary_credential</code></b><i>Also known as:</i> request_token — Returns the temporary credential for this client.<br>
<h4>Returns</h4>
(<a href='SignetOAuth1Credential.md'>Signet::OAuth1::Credential</a>) — The temporary credentials.<br />
<h3>Method: <code>Signet::OAuth1::Client#temporary_credential=</code></h3>
(Object)  <b><code>temporary_credential=</code></b> <code>(new_temporary_credential)</code><i>Also known as:</i> request_token= — Sets the temporary credential for this client.<br>
<h4>Parameters</h4>
(<a href='SignetOAuth1Credential.md'>Signet::OAuth1::Credential</a>) <b><code>new_temporary_credential</code></b> — The temporary credentials.<br />
<h3>Method: <code>Signet::OAuth1::Client#temporary_credential_key</code></h3>
(String)  <b><code>temporary_credential_key</code></b><i>Also known as:</i> request_token_key — Returns the temporary credential key for this client.<br>
<h4>Returns</h4>
(String) — The temporary credential key.<br />
<h3>Method: <code>Signet::OAuth1::Client#temporary_credential_key=</code></h3>
(Object)  <b><code>temporary_credential_key=</code></b> <code>(new_temporary_credential_key)</code><i>Also known as:</i> request_token_key= — Sets the temporary credential key for this client.<br>
<h4>Parameters</h4>
(String, #to_str) <b><code>new_temporary_credential_key</code></b> — The temporary credential key.<br />
<h3>Method: <code>Signet::OAuth1::Client#temporary_credential_secret</code></h3>
(String)  <b><code>temporary_credential_secret</code></b><i>Also known as:</i> request_token_secret — Returns the temporary credential secret for this client.<br>
<h4>Returns</h4>
(String) — The temporary credential secret.<br />
<h3>Method: <code>Signet::OAuth1::Client#temporary_credential_secret=</code></h3>
(Object)  <b><code>temporary_credential_secret=</code></b> <code>(new_temporary_credential_secret)</code><i>Also known as:</i> request_token_secret= — Sets the temporary credential secret for this client.<br>
<h4>Parameters</h4>
(String, #to_str) <b><code>new_temporary_credential_secret</code></b> — The temporary credential secret.<br />
<h3>Method: <code>Signet::OAuth1::Client#temporary_credential_uri</code></h3>
(Addressable::URI)  <b><code>temporary_credential_uri</code></b><i>Also known as:</i> request_token_uri — Returns the temporary credentials URI for this client.<br>
<h4>Returns</h4>
(Addressable::URI) — The temporary credentials URI.<br />
<h3>Method: <code>Signet::OAuth1::Client#temporary_credential_uri=</code></h3>
(Object)  <b><code>temporary_credential_uri=</code></b> <code>(new_temporary_credential_uri)</code><i>Also known as:</i> request_token_uri= — Sets the temporary credentials URI for this client.<br>
<h4>Parameters</h4>
(Addressable::URI, String, #to_str) <b><code>new_temporary_credential_uri</code></b> — The temporary credentials URI.<br />
<h3>Method: <code>Signet::OAuth1::Client#token_credential</code></h3>
(<a href='SignetOAuth1Credential.md'>Signet::OAuth1::Credential</a>)  <b><code>token_credential</code></b><i>Also known as:</i> access_token — Returns the token credential for this client.<br>
<h4>Returns</h4>
(<a href='SignetOAuth1Credential.md'>Signet::OAuth1::Credential</a>) — The token credentials.<br />
<h3>Method: <code>Signet::OAuth1::Client#token_credential=</code></h3>
(Object)  <b><code>token_credential=</code></b> <code>(new_token_credential)</code><i>Also known as:</i> access_token= — Sets the token credential for this client.<br>
<h4>Parameters</h4>
(<a href='SignetOAuth1Credential.md'>Signet::OAuth1::Credential</a>) <b><code>new_token_credential</code></b> — The token credentials.<br />
<h3>Method: <code>Signet::OAuth1::Client#token_credential_key</code></h3>
(String)  <b><code>token_credential_key</code></b><i>Also known as:</i> access_token_key — Returns the token credential key for this client.<br>
<h4>Returns</h4>
(String) — The token credential key.<br />
<h3>Method: <code>Signet::OAuth1::Client#token_credential_key=</code></h3>
(Object)  <b><code>token_credential_key=</code></b> <code>(new_token_credential_key)</code><i>Also known as:</i> access_token_key= — Sets the token credential key for this client.<br>
<h4>Parameters</h4>
(String, #to_str) <b><code>new_token_credential_key</code></b> — The token credential key.<br />
<h3>Method: <code>Signet::OAuth1::Client#token_credential_secret</code></h3>
(String)  <b><code>token_credential_secret</code></b><i>Also known as:</i> access_token_secret — Returns the token credential secret for this client.<br>
<h4>Returns</h4>
(String) — The token credential secret.<br />
<h3>Method: <code>Signet::OAuth1::Client#token_credential_secret=</code></h3>
(Object)  <b><code>token_credential_secret=</code></b> <code>(new_token_credential_secret)</code><i>Also known as:</i> access_token_secret= — Sets the token credential secret for this client.<br>
<h4>Parameters</h4>
(String, #to_str) <b><code>new_token_credential_secret</code></b> — The token credential secret.<br />
<h3>Method: <code>Signet::OAuth1::Client#token_credential_uri</code></h3>
(Addressable::URI)  <b><code>token_credential_uri</code></b><i>Also known as:</i> access_token_uri — Returns the token credential URI for this client.<br>
<h4>Returns</h4>
(Addressable::URI) — The token credential URI.<br />
<h3>Method: <code>Signet::OAuth1::Client#token_credential_uri=</code></h3>
(Object)  <b><code>token_credential_uri=</code></b> <code>(new_token_credential_uri)</code><i>Also known as:</i> access_token_uri= — Sets the token credential URI for this client.<br>
<h4>Parameters</h4>
(Addressable::URI, String, #to_str) <b><code>new_token_credential_uri</code></b> — The token credential URI.<br />
<h3>Method: <code>Signet::OAuth1::Client#two_legged</code></h3>
(TrueClass, FalseClass)  <b><code>two_legged</code></b> — Returns whether the client is in two-legged mode.<br>
<h4>Returns</h4>
(TrueClass, FalseClass) — <code>true&lt;/code&gt; for two-legged mode, &lt;code&gt;false</code> otherwise.<br />
<h3>Method: <code>Signet::OAuth1::Client#two_legged=</code></h3>
(Object)  <b><code>two_legged=</code></b> <code>(new_two_legged)</code> — Sets the client for two-legged mode.<br>
<h4>Parameters</h4>
(TrueClass, FalseClass) <b><code>new_two_legged</code></b> — <code>true&lt;/code&gt; for two-legged mode, &lt;code&gt;false</code> otherwise.<br />
<hr />
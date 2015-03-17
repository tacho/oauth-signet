<h1>Signet</h1>
<dl>
<blockquote><dt>Homepage</dt><dd><a href='http://code.google.com/p/oauth-signet/'><a href='http://code.google.com/p/oauth-signet/'>http://code.google.com/p/oauth-signet/</a></a></dd>
<dt>Author</dt><dd><a href='mailto:bobaman@google.com'>Bob Aman</a></dd>
<dt>Copyright</dt><dd>Copyright © 2010 Google, Inc.</dd>
<dt>License</dt><dd>Apache 2.0</dd>
</dl>
<h2>Description</h2>
<p>Signet is an OAuth 1.0 / OAuth 2.0 implementation.</p>
<h2>Reference</h2>
<ul>
<li><a href='SignetOAuth1.md'>Signet::OAuth1</a></li>
<li><a href='SignetOAuth1Client.md'>Signet::OAuth1::Client</a></li>
<li><a href='SignetOAuth1Credential.md'>Signet::OAuth1::Credential</a></li>
<li><a href='SignetOAuth2.md'>Signet::OAuth2</a></li>
<li><a href='SignetOAuth2Client.md'>Signet::OAuth2::Client</a></li>
</ul>
<h2>Example Usage for Google</h2>
<pre><code>require 'signet/oauth_1/client'<br>
client = Signet::OAuth1::Client.new(<br>
  :temporary_credential_uri =&gt;<br>
    'https://www.google.com/accounts/OAuthGetRequestToken',<br>
  :authorization_uri =&gt;<br>
    'https://www.google.com/accounts/OAuthAuthorizeToken',<br>
  :token_credential_uri =&gt;<br>
    'https://www.google.com/accounts/OAuthGetAccessToken',<br>
  :client_credential_key =&gt; 'anonymous',<br>
  :client_credential_secret =&gt; 'anonymous'<br>
)<br>
client.fetch_temporary_credential!(:additional_parameters =&gt; {<br>
  :scope =&gt; 'https://mail.google.com/mail/feed/atom'<br>
})<br>
# Send the user to client.authorization_uri, obtain verifier<br>
client.fetch_token_credential!(:verifier =&gt; '12345')<br>
response = client.fetch_protected_resource(<br>
  :uri =&gt; 'https://mail.google.com/mail/feed/atom'<br>
)<br>
</code></pre>
<h2>Install</h2>
<p><code>sudo gem install signet</code></p>
<p>Be sure <code>http://rubygems.org/</code> is in your gem sources.</p>
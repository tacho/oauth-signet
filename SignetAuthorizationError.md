# Exception: Signet::AuthorizationError #
<dl>
<blockquote><dt>Inherits:</dt>
<dd>Object > StandardError > Signet::AuthorizationError</dd>
<dt>Defined in:</dt>
<dd><code>lib/signet/errors.rb</code></dd>
</dl>
<h2>Overview</h2>
An error indicating the server refused to authorize the client.<br>
<h2>Constructor Details</h2>
<h3>Method: <code>Signet::AuthorizationError#initialize</code></h3>
(AuthorizationError)  <b><code>initialize</code></b> <code>(message, options = {})</code> — Creates a new authentication error.<br>
<h4>Parameters</h4>
(String) <b><code>message</code></b> — A message describing the error.<br />
(Hash) <b><code>options</code></b> <i>(defaults to: <code>{}</code>)</i> — The configuration parameters for the request.<br>
- <code>:request</code> —<br>
A Faraday::Request object.  Optional.<br>
- <code>:response</code> —<br>
A Faraday::Response object.  Optional.<br>
- <code>:code</code> —<br>
An error code.<br>
- <code>:description</code> —<br>
Human-readable text intended to be used to assist in resolving the<br>
error condition.<br>
- <code>:uri</code> —<br>
A URI identifying a human-readable web page with additional<br>
information about the error, indended for the resource owner.<br />
<hr />
<h2>Instance Attribute Details</h2>
<h3>Method: <code>Signet::AuthorizationError#request</code></h3>
(Array)  <b><code>request</code></b> <span>(readonly)</span> — The HTTP request that triggered this authentication error.<br>
<h4>Returns</h4>
(Array) — A tuple of method, uri, headers, and body.<br />
<h3>Method: <code>Signet::AuthorizationError#response</code></h3>
(Array)  <b><code>response</code></b> <span>(readonly)</span> — The HTTP response that triggered this authentication error.<br>
<h4>Returns</h4>
(Array) — A tuple of status, headers, and body.<br />
<hr />
# Class: Signet::OAuth1::Credential #
<dl>
<blockquote><dt>Inherits:</dt>
<dd>Object > Signet::OAuth1::Credential</dd>
<dt>Defined in:</dt>
<dd><code>lib/signet/oauth_1/credential.rb</code></dd>
</dl>
<h2>Constructor Details</h2>
<h3>Method: <code>Signet::OAuth1::Credential#initialize</code></h3>
(Credential)  <b><code>initialize</code></b> <code>(*args)</code> — Creates a token object from a key and secret.<br>
<h4>Examples</h4>
<h5></h5>
<pre><code>Signet::OAuth1::Credential.new(<br>
  :key =&gt; "dpf43f3p2l4k3l03",<br>
  :secret =&gt; "kd94hf93k423kf44"<br>
)<br>
</code></pre>
<h5></h5>
<pre><code>Signet::OAuth1::Credential.new([<br>
  ["oauth_token", "dpf43f3p2l4k3l03"],<br>
  ["oauth_token_secret", "kd94hf93k423kf44"]<br>
])<br>
</code></pre>
<h5></h5>
<pre><code>Signet::OAuth1::Credential.new(<br>
  "dpf43f3p2l4k3l03", "kd94hf93k423kf44"<br>
)<br>
</code></pre>
<hr />
<h2>Instance Attribute Details</h2>
<h3>Method: <code>Signet::OAuth1::Credential#key</code></h3>
(Object)  <b><code>key</code></b> — Returns the value of attribute key<br>
<h3>Method: <code>Signet::OAuth1::Credential#secret</code></h3>
(Object)  <b><code>secret</code></b> — Returns the value of attribute secret<br>
<hr />
<h2>Instance Method Details</h2>
<h3>Method: <code>Signet::OAuth1::Credential#==</code></h3>
(Object)  <b><code>==</code></b> <code>(other)</code> —<br>
<h3>Method: <code>Signet::OAuth1::Credential#to_hash</code></h3>
(Object)  <b><code>to_hash</code></b><i>Also known as:</i> to_h —<br>
<hr />
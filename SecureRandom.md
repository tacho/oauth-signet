# Module: SecureRandom #
<dl>
<blockquote><dt>Defined in:</dt>
<dd><code>lib/compat/securerandom.rb</code></dd>
</dl>
<hr />
<h2>Class Method Details</h2>
<h3>Method: <code>SecureRandom.base64</code></h3>
(Object)  <b><code>base64</code></b> <code>(n = nil)</code> — SecureRandom.base64 generates a random base64 string.<br>
The argument n specifies the length of the random length.<br>
The length of the result string is about 4/3 of n.<br>
If n is not specified, 16 is assumed.<br>
It may be larger in future.<br>
If secure random number generator is not available,<br>
NotImplementedError is raised.<br>
<h3>Method: <code>SecureRandom.hex</code></h3>
(Object)  <b><code>hex</code></b> <code>(n = nil)</code> — SecureRandom.hex generates a random hex string.<br>
The argument n specifies the length of the random length.<br>
The length of the result string is twice of n.<br>
If n is not specified, 16 is assumed.<br>
It may be larger in future.<br>
If secure random number generator is not available,<br>
NotImplementedError is raised.<br>
<h3>Method: <code>SecureRandom.lastWin32ErrorMessage</code></h3>
(Object)  <b><code>lastWin32ErrorMessage</code></b> — Following code is based on David Garamond's GUID library for Ruby.<br>
<h3>Method: <code>SecureRandom.random_bytes</code></h3>
(Object)  <b><code>random_bytes</code></b> <code>(n = nil)</code> — SecureRandom.random_bytes generates a random binary string.<br>
The argument n specifies the length of the result string.<br>
If n is not specified, 16 is assumed.<br>
It may be larger in future.<br>
If secure random number generator is not available,<br>
NotImplementedError is raised.<br>
<h4>Raises</h4>
(NotImplementedError) <br />
<h3>Method: <code>SecureRandom.random_number</code></h3>
(Object)  <b><code>random_number</code></b> <code>(n = 0)</code> —<br>
<hr />
# Module: Signet::OAuth1 #
<dl>
<blockquote><dt>Defined in:</dt>
<dd><code>lib/signet/oauth_1.rb</code>, <code>lib/signet/oauth_1/client.rb</code>, <code>lib/signet/oauth_1/credential.rb</code>, <code>lib/signet/oauth_1/signature_methods/hmac_sha1.rb</code></dd>
</dl>
<h2>Defined Under Namespace</h2>
<h3>Modules</h3>
</blockquote>  * [HMACSHA1](SignetOAuth1HMACSHA1.md)
### Classes ###
  * [Client](SignetOAuth1Client.md)
  * [Credential](SignetOAuth1Credential.md)
## Constant Summary ##
<dl>
<dt><code>OUT_OF_BAND</code> = </dt>
<dd>
<pre><code>'oob'<br>
</code></pre>
</dd>
</dl>

---

## Class Method Details ##
### Method: `Signet::OAuth1.encode` ###
(String)  **`encode`** `(value)` — Converts a value to a percent-encoded `String` according to
the rules given in RFC 5849.  All non-unreserved characters are
percent-encoded.
#### Parameters ####
(Symbol, #to\_str) **`value`** — The value to be encoded.<br />
#### Returns ####
(String) — The percent-encoded value.<br />
### Method: `Signet::OAuth1.extract_credential_key_option` ###
(String)  **`extract_credential_key_option`** `(credential_type, options)` — Processes an options `Hash` to find a credential key value.
Allows for greater flexibility in configuration.
#### Parameters ####
(Symbol) **`credential_type`** — One of `:client</code>, <code>:temporary`,
`:token</code>, <code>:consumer</code>, <code>:request`,
or `:access`.<br />
#### Returns ####
(String) — The credential key value.<br />
### Method: `Signet::OAuth1.extract_credential_secret_option` ###
(String)  **`extract_credential_secret_option`** `(credential_type, options)` — Processes an options `Hash` to find a credential secret value.
Allows for greater flexibility in configuration.
#### Parameters ####
(Symbol) **`credential_type`** — One of `:client</code>, <code>:temporary`,
`:token</code>, <code>:consumer</code>, <code>:request`,
or `:access`.<br />
#### Returns ####
(String) — The credential secret value.<br />
### Method: `Signet::OAuth1.generate_authorization_header` ###
(String)  **`generate_authorization_header`** `(parameters, realm = nil)` — Generates an `Authorization` header from a parameter list
according to the rules given in RFC 5849.
#### Parameters ####
(Enumerable) **`parameters`** — The OAuth parameter list.<br />
(String) **`realm`** _(defaults to: `nil`)_ — The `Authorization` realm.  See RFC 2617.<br />
#### Returns ####
(String) — The `Authorization` header.<br />
### Method: `Signet::OAuth1.generate_authorization_uri` ###
(String)  **`generate_authorization_uri`** `(authorization_uri, options = {})` — Appends the optional 'oauth\_token' and 'oauth\_callback' parameters to
the base authorization URI.
#### Parameters ####
(Addressable::URI, String, #to\_str) **`authorization_uri`** — The base authorization URI.<br />
#### Returns ####
(String) — The authorization URI to redirect the user to.<br />
### Method: `Signet::OAuth1.generate_base_string` ###
(String)  **`generate_base_string`** `(method, uri, parameters)` — Generates a signature base string according to the algorithm given in
RFC 5849.  Joins the method, URI, and normalized parameter string with
'&' characters.
#### Parameters ####
(String) **`method`** — The HTTP method.<br />
(Addressable::URI, String, #to\_str) **`The`** — URI.<br />
(Enumerable) **`parameters`** — The OAuth parameter list.<br />
#### Returns ####
(String) — The signature base string.<br />
### Method: `Signet::OAuth1.generate_nonce` ###
(String)  **`generate_nonce`** — Returns a nonce suitable for use as an `'oauth_nonce'`
value.
#### Returns ####
(String) — A random nonce.<br />
### Method: `Signet::OAuth1.generate_timestamp` ###
(String)  **`generate_timestamp`** — Returns a timestamp suitable for use as an `'oauth_timestamp'`
value.
#### Returns ####
(String) — The current timestamp.<br />
### Method: `Signet::OAuth1.normalize_parameters` ###
(String)  **`normalize_parameters`** `(parameters)` — Normalizes a set of OAuth parameters according to the algorithm given
in RFC 5849.  Sorts key/value pairs lexically by byte order, first by
key, then by value, joins key/value pairs with the '=' character, then
joins the entire parameter list with '&' characters.
#### Parameters ####
(Enumerable) **`parameters`** — The OAuth parameter list.<br />
#### Returns ####
(String) — The normalized parameter list.<br />
### Method: `Signet::OAuth1.parse_authorization_header` ###
(Object)  **`parse_authorization_header`** `(field_value)` — Parses an `Authorization` header into its component
parameters.  Parameter keys and values are decoded according to the
rules given in RFC 5849.
### Method: `Signet::OAuth1.parse_form_encoded_credentials` ###
([Signet::OAuth1::Credential](SignetOAuth1Credential.md))  **`parse_form_encoded_credentials`** `(body)` — Parses an `application/x-www-form-urlencoded` HTTP response
body into an OAuth key/secret pair.
#### Parameters ####
(String) **`body`** — The response body.<br />
#### Returns ####
([Signet::OAuth1::Credential](SignetOAuth1Credential.md)) — The OAuth credentials.<br />
### Method: `Signet::OAuth1.sign_parameters` ###
(String)  **`sign_parameters`** `(method, uri, parameters, client_credential_secret, token_credential_secret = nil)` — Generates an OAuth signature using the signature method indicated in the
parameter list.  Unsupported signature methods will result in a
`NotImplementedError` exception being raised.
#### Parameters ####
(String) **`method`** — The HTTP method.<br />
(Addressable::URI, String, #to\_str) **`The`** — URI.<br />
(Enumerable) **`parameters`** — The OAuth parameter list.<br />
(String) **`client_credential_secret`** — The client credential secret.<br />
(String) **`token_credential_secret`** _(defaults to: `nil`)_ — The token credential secret.  Omitted when unavailable.<br />
#### Returns ####
(String) — The signature.<br />
### Method: `Signet::OAuth1.unencode` ###
(String)  **`unencode`** `(value)` — Converts a percent-encoded String to an unencoded value.
#### Parameters ####
(#to\_str) **`value`** — The percent-encoded `String` to be unencoded.<br />
#### Returns ####
(String) — The unencoded value.<br />
### Method: `Signet::OAuth1.unsigned_resource_parameters` ###
(Array)  **`unsigned_resource_parameters`** `(options = {})` — Generates an OAuth parameter list to be used when requesting a
protected resource.
#### Parameters ####
(Hash) **`options`** _(defaults to: `{}`)_ — The configuration parameters for the request.
- `:client_credential_key` —
> > The client credential key.
- `:token_credential_key` —
> > The token credential key.
- `:signature_method` —
> > The signature method.  Defaults to `'HMAC-SHA1'`.
- `:two_legged` —
> > A switch for two-legged OAuth.  Defaults to `false`.<br />
#### Returns ####
(Array) — The parameter list as an `Array` of key/value pairs.<br />
### Method: `Signet::OAuth1.unsigned_temporary_credential_parameters` ###
(Array)  **`unsigned_temporary_credential_parameters`** `(options = {})` — Generates an OAuth parameter list to be used when obtaining a set of
temporary credentials.
#### Parameters ####
(Hash) **`options`** _(defaults to: `{}`)_ — The configuration parameters for the request.
- `:client_credential_key` —
> > The client credential key.
- `:callback` —
> > The OAuth callback.  Defaults to {Signet::OAuth1::OUT\_OF\_BAND}.
- `:signature_method` —
> > The signature method.  Defaults to `'HMAC-SHA1'`.
- `:additional_parameters` —
> > Non-standard additional parameters.<br />
#### Returns ####
(Array) — The parameter list as an `Array` of key/value pairs.<br />
### Method: `Signet::OAuth1.unsigned_token_credential_parameters` ###
(Array)  **`unsigned_token_credential_parameters`** `(options = {})` — Generates an OAuth parameter list to be used when obtaining a set of
token credentials.
#### Parameters ####
(Hash) **`options`** _(defaults to: `{}`)_ — The configuration parameters for the request.
- `:client_credential_key` —
> > The client credential key.
- `:temporary_credential_key` —
> > The temporary credential key.
- `:verifier` —
> > The OAuth verifier.
- `:signature_method` —
> > The signature method.  Defaults to `'HMAC-SHA1'`.<br />
#### Returns ####
(Array) — The parameter list as an `Array` of key/value pairs.<br />

---

# Module: Signet::OAuth2 #
<dl>
<blockquote><dt>Defined in:</dt>
<dd><code>lib/signet/oauth_2.rb</code>, <code>lib/signet/oauth_2/client.rb</code></dd>
</dl>
<h2>Overview</h2>
An implementation of <a href='http://tools.ietf.org/html/draft-ietf-oauth-v2-10'>http://tools.ietf.org/html/draft-ietf-oauth-v2-10</a>
This module will be updated periodically to support newer drafts of the<br>
specification, as they become widely deployed.<br>
<h2>Defined Under Namespace</h2>
<h3>Classes</h3>
</blockquote>  * [Client](SignetOAuth2Client.md)

---

## Class Method Details ##
### Method: `Signet::OAuth2.generate_authorization_uri` ###
(String)  **`generate_authorization_uri`** `(authorization_uri, parameters = {})` — Appends the necessary OAuth parameters to
the base authorization endpoint URI.
#### Parameters ####
(Addressable::URI, String, #to\_str) **`authorization_uri`** — The base authorization endpoint URI.<br />
#### Returns ####
(String) — The authorization URI to redirect the user to.<br />
### Method: `Signet::OAuth2.generate_basic_authorization_header` ###
(String)  **`generate_basic_authorization_header`** `(client_id, client_password)` — Generates a Basic Authorization header from a client identifier and a
client password.
#### Parameters ####
(String) **`client_id`** — The client identifier.<br />
(String) **`client_password`** — The client password.<br />
#### Returns ####
(String) — The value for the HTTP Basic Authorization header.<br />
### Method: `Signet::OAuth2.generate_bearer_authorization_header` ###
(String)  **`generate_bearer_authorization_header`** `(access_token, auth_params = nil)` — Generates a Basic Authorization header from a client identifier and a
client password.
#### Parameters ####
(String) **`client_id`** — The client identifier.<br />
(String) **`client_password`** — The client password.<br />
#### Returns ####
(String) — The value for the HTTP Basic Authorization header.<br />
### Method: `Signet::OAuth2.parse_authorization_header` ###
(Object)  **`parse_authorization_header`** `(field_value)` —
### Method: `Signet::OAuth2.parse_basic_credentials` ###
(Object)  **`parse_basic_credentials`** `(credential_string)` —
### Method: `Signet::OAuth2.parse_bearer_credentials` ###
(Object)  **`parse_bearer_credentials`** `(credential_string)` —
### Method: `Signet::OAuth2.parse_json_credentials` ###
(Object)  **`parse_json_credentials`** `(body)` —
### Method: `Signet::OAuth2.parse_oauth_challenge` ###
(Object)  **`parse_oauth_challenge`** `(challenge_string)` —
### Method: `Signet::OAuth2.parse_www_authenticate_header` ###
(Object)  **`parse_www_authenticate_header`** `(field_value)` —

---

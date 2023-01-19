# Awesome Faraday

A curated list of awesome middleware and adapters for Faraday.
If you want your adapter or middleware to feature in this list, please open a [discussion](https://github.com/lostisland/awesome-faraday/discussions) or a PR.

## Adapters

Faraday allows you to change the adapter, the element in the stack responsible for performing the HTTP request, with ease, by the combination of a standardised API to provide configuration and request details, and a powerful set of middleware.
However, each adapter can also offer unique features, or lack the support for others.
The following table show the available adapters and which features they support.

| Adapter | Bundled with Faraday | Reason Phrase parsing | Compression (Gzip, Deflate) | Response Streaming | Parallel Requests | GET, HEAD, DELETE, TRACE Request Body | HEAD Response Body | TRACE Method | Local Socket Binding |
| ----------------------- |  :---:  | :----: | :----: | :----: | :----: | :----: | :----: | :----: | :----: |
| [EM::HTTP]              | v1 only |   ✔️   |   ✖️   |   ✖️   |   ✔️   |   ✔️   |   ✖️   |   ✔️   |   ✔️   |
| [EM::Synchrony]         | v1 only |   ✔️   |   ✖️   |   ✖️   |   ✔️   |   ✔️   |   ✖️   |   ✔️   |   ✔️   |
| [Excon]                 | v1 only |   ✔️   |   ✖️   |   ✖️   |   ✖️   |   ✔️   |   ✔️   |   ✔️   |   ✖️   |
| [HttpClient]            | v1 only |   ✔️   |   ✔️   |   ✖️   |   ✖️   |   ✔️   |   ✔️   |   ✔️   |   ✔️   |
| [Net::HTTP]             |   ✔️     |   ✔️   |   ✔️   |   ✔️   |   ✖️   |   ✔️   |   ✔️   |   ✔️   |   ✖️   |
| [Net::HTTP::Persistent] | v1 only |   ✔️   |   ✔️   |   ✖️   |   ✖️   |   ✔️   |   ✔️   |   ✔️   |   ✖️   |
| [Patron]                | v1 only |   ✔️   |   ✖️   |   ✖️   |   ✖️   |   ✖️   |   ✔️   |   ✖️   |   ✖️   |
| [Typhoeus]              | v1 only |   ✔️   |   ✔️   |   ✔️   |   ✔️   |   ✔️   |   ✔️   |   ✔️   |   ✖️   |
| [HTTP.rb]               |   ✖️     |   ✔️   |   ✖️   |   ✖️   |   ✖️   |   ✔️   |   ✖️   |   ✔️   |   ✔️   |
| [httpx]                 |   ✖️     |   ✔️   |   ✔️   |   ✔️   |   ✔️   |   ✔️   |   ✔️   |   ✔️   |   ✔️   |


## Middleware

Under the hood, Faraday uses a Rack-inspired middleware stack for making requests. Much of Faraday’s power is unlocked with custom middleware. Some middleware is included with Faraday, and others are in external gems. [Learn more about Middleware](https://lostisland.github.io/faraday/middleware/).

In addition to this curated list of middleware, we would like to specifically call your attention to middleware that is helpful for general HTTP use:

- [encoding](https://github.com/ma2gedev/faraday-encoding) - required for handling UTF-8 responses
- [follow_redirects](https://github.com/tisba/faraday-follow-redirects) - follow HTTP 30X redirects
- [json_request](https://lostisland.github.io/faraday/middleware/json-request) and [json_response](https://lostisland.github.io/faraday/middleware/json-response) - encode/decode JSON requests and responses
- [parse_dates](https://github.com/AlexWayfer/faraday-parse_dates) - parse ISO 8601 dates from response body
- [retry](https://github.com/lostisland/faraday-retry) - retry intermittent HTTP failures
- [url_encoded](https://lostisland.github.io/faraday/middleware/url-encoded) - encode request body as a url-encoded form upload

#### Awesome Community Middleware

- [cookie_jar](https://github.com/miyagawa/faraday-cookie_jar) - support for HTTP cookies
- [detailed_logger](https://github.com/envylabs/faraday-detailed_logger) - robust logging for requests & responses
- [encoding](https://github.com/ma2gedev/faraday-encoding) - required for handling UTF-8 responses
- [http_cache](https://github.com/sourcelevel/faraday-http-cache) - standards compliant cache that works with [ActiveSupport::Cache](https://api.rubyonrails.org/classes/ActiveSupport/Cache/Store.html)
- [gzip](https://github.com/bodrovis/faraday-gzip) - decompress responses (needed for some non-default adapters)
- [jwt](https://github.com/nov/faraday-jwt) - JWT request encode & response decode with optional signing & verifications

#### Included with `faraday` itself

- [authorization](https://github.com/lostisland/faraday/blob/main/lib/faraday/request/authorization.rb) - middleware for the Authorization HTTP header
- [basic_authentication](https://lostisland.github.io/faraday/middleware/authentication) - HTTP basic auth
- [instrumentation](https://lostisland.github.io/faraday/middleware/instrumentation) - instrument requests using [ActiveSupport::Notifications](https://api.rubyonrails.org/classes/ActiveSupport/Notifications.html) or similar
- [logger](https://lostisland.github.io/faraday/middleware/logger) - log request and response
- [raise_error](https://lostisland.github.io/faraday/middleware/raise-error) - raises exception on 4xx or 5xx
- [token_authentication](https://lostisland.github.io/faraday/middleware/authentication) - HTTP token authentication
- [url_encoded](https://lostisland.github.io/faraday/middleware/url-encoded) - encode request body as a url-encoded form upload
- [json](https://github.com/lostisland/faraday_middleware) - encode/decode JSON requests and responses

#### Bundled into their own gems

- [multipart](https://github.com/lostisland/faraday-multipart) - encode request body as a multipart form
- [retry](https://github.com/lostisland/faraday-retry) - retry intermittent HTTP failures
- [rashify](https://github.com/lostisland/faraday-rashify) - parse responses into a [Hashie::Mash::Rash](https://github.com/hashie/hashie)
- [follow_redirects](https://github.com/tisba/faraday-follow-redirects) - follow HTTP 30X redirects
- [encode_xml](https://github.com/AlexWayfer/faraday-encode_xml) - encode XML requests (responses decoding is included in `faraday_middleware` gem)
- [decode_xml](https://github.com/soberstadt/faraday-decode_xml) - decode XML responses
- [`XML Middleware`](https://github.com/gemhome/faraday-xml) - parses response body into a hash of key/value pairs.

#### `faraday_middleware` gem

ATTENTION: `faraday_middleware` have been deprecated and won't be updated to work on Faraday 2.0.
All the middleware below will need to be moved into their own gems.

- [caching](https://github.com/lostisland/faraday_middleware/blob/main/docs/caching_responses.md) - simple cache that works with [ActiveSupport::Cache](https://api.rubyonrails.org/classes/ActiveSupport/Cache/Store.html)
- [chunked](https://github.com/lostisland/faraday_middleware/blob/main/lib/faraday_middleware/response/chunked.rb) - support for HTTP Transfer-Encoding
- [dates](https://github.com/lostisland/faraday_middleware/blob/main/lib/faraday_middleware/response/parse_dates.rb) - parse ISO 8601 dates from response body
- [follow_redirects](https://github.com/lostisland/faraday_middleware/blob/main/lib/faraday_middleware/response/follow_redirects.rb) - follow HTTP 30X redirects
- [instrumentation](https://github.com/lostisland/faraday_middleware/blob/main/lib/faraday_middleware/instrumentation.rb) - instruments requests using [ActiveSupport::Notifications](https://api.rubyonrails.org/classes/ActiveSupport/Notifications.html) or similar
- [json_fix](https://github.com/lostisland/faraday_middleware/blob/main/lib/faraday_middleware/response/parse_json.rb) - fix responses that insist on serving JSON with wrong mime types
- [marshal](https://github.com/lostisland/faraday_middleware/blob/main/lib/faraday_middleware/response/parse_marshal.rb) - parse responses as marshalled ruby objects
- [mashify](https://github.com/lostisland/faraday_middleware/blob/main/lib/faraday_middleware/response/mashify.rb) - parse responses into a [Hashie::Mash](https://github.com/hashie/hashie)
- [method_override](https://github.com/lostisland/faraday_middleware/blob/main/docs/method_override.md) - support for X-Http-Method-Override
- [oauth/oauth2](https://github.com/lostisland/faraday_middleware/blob/main/docs/oauth.md) - adds an oauth access token to each request
- [rashify](https://github.com/lostisland/faraday_middleware/blob/main/lib/faraday_middleware/response/rashify.rb) - parse responses into a [Hashie::Rash](https://github.com/hashie/hashie)
- [xml](https://github.com/lostisland/faraday_middleware/blob/main/lib/faraday_middleware/response/parse_xml.rb) - parse responses as XML
- [yaml](https://github.com/lostisland/faraday_middleware/blob/main/lib/faraday_middleware/response/parse_yaml.rb) - parse responses as YAML

## Tooling

- [faraday-logging-color_formatter](https://github.com/kobusjoubert/faraday-logging-color_formatter) - A color formatter for the default Faraday logger


[EM::HTTP]:               https://github.com/lostisland/faraday-em_http
[EM::Synchrony]:          https://github.com/lostisland/faraday-em_synchrony
[Excon]:                  https://github.com/lostisland/faraday-excon
[HttpClient]:             https://github.com/lostisland/faraday-httpclient
[Net::HTTP]:              https://github.com/lostisland/faraday-net_http
[Net::HTTP::Persistent]:  https://github.com/lostisland/faraday-net_http_persistent
[Patron]:                 https://github.com/lostisland/faraday-patron
[Typhoeus]:               https://github.com/dleavitt/faraday-typhoeus
[HTTP.rb]:                https://github.com/lostisland/faraday-http
[httpx]:                  https://honeyryderchuck.gitlab.io/httpx/wiki/Faraday-Adapter

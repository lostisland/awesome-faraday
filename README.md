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
| [Net::HTTP]             | v1 only |   ✔️   |   ✔️   |   ✔️   |   ✖️   |   ✔️   |   ✔️   |   ✔️   |   ✖️   |
| [Net::HTTP::Persistent] | v1 only |   ✔️   |   ✔️   |   ✖️   |   ✖️   |   ✔️   |   ✔️   |   ✔️   |   ✖️   |
| [Patron]                | v1 only |   ✔️   |   ✖️   |   ✖️   |   ✖️   |   ✖️   |   ✔️   |   ✖️   |   ✖️   |
| [Typhoeus]              | v1 only |   ✖️   |   ✖️   |   ✖️   |   ✔️   |   ✔️   |   ✔️   |   ✔️   |   ✖️   |
| [HTTP.rb]               |   ✖️    |   ✔️   |   ✖️   |   ✖️   |   ✖️   |   ✔️   |   ✖️   |   ✔️   |   ✔️   |

## Middleware

Under the hood, Faraday uses a Rack-inspired middleware stack for making requests. Much of Faraday’s power is unlocked with custom middleware. Some middleware is included with Faraday, and others are in external gems. [Learn more about Middleware](https://lostisland.github.io/faraday/usage/).

### Body Types

TBC

[EM::HTTP]:               https://github.com/lostisland/faraday-em_http
[EM::Synchrony]:          https://github.com/lostisland/faraday-em_synchrony
[Excon]:                  https://github.com/lostisland/faraday-excon
[HttpClient]:             https://github.com/lostisland/faraday/blob/main/lib/faraday/adapter/httpclient.rb
[Net::HTTP]:              https://github.com/lostisland/faraday-net_http
[Net::HTTP::Persistent]:  https://github.com/lostisland/faraday-net_http_persistent
[Patron]:                 https://github.com/lostisland/faraday/blob/main/lib/faraday/adapter/httpclient.rb
[Typhoeus]:               https://github.com/typhoeus/typhoeus/blob/master/lib/typhoeus/adapters/faraday.rb
[HTTP.rb]:                https://github.com/lostisland/faraday-http

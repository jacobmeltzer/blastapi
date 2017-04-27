---
title: Blast API Reference

language_tabs:
  - shell

toc_footers:
  - <a href='http://24b3f761.ngrok.io/register'>Sign Up for Key</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - lists
  - incoming
  - outgoing
  - errors

search: true
---

# Introduction

Welcome to the Blast API! You can use our API to create incoming and outgoing campaigns, manage contact lists, add contacts to your account, etc.

This example API documentation page, including some boilerplate text, was created with [Slate](https://github.com/tripit/slate).

# Authentication

Our API authentication is based on HTTP Basic Authentication. We require your account username as the basic authentication username, as well as your API key as the basic authentication password. 
> To authorize, use this code:

```shell
# With shell, you can just pass the correct header with each request
curl "http://24b3f761.ngrok.io/api/incoming"
  -u username:key
```

> Make sure to replace `username` with your username and `token` with your API key.

Blast uses API keys to allow access to the API. You can register a new API key by creating an account in our [portal](http://24b3f761.ngrok.io/register).

Blast expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: Basic encodedKey`

<aside class="notice">
You must replace <code>encodedKey</code> with your encoded key.
</aside>


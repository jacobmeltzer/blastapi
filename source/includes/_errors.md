# Errors

The Blast API uses the following error codes. Additionally, upon error, an error field will be set in the JSON response.

Error Code | Meaning
---------- | -------
401 | Unauthorized -- Invalid API key/username.
404 | Not Found -- The specified kitten could not be found
500 | Internal Server Error -- We had a problem with our server. Try again later.
---
title: Authentication
position: 2
right_code: |
  ~~~ bash
  curl -X POST https://learn.saylor.org/webservice/rest/server.php --data "wstoken=YOUR_API_TOKEN&wsfunction=YOUR_FUNCTION_NAME&YOUR_FUNCTION_PARAMETERS=YOUR_FUNCTION_VALUES" -v
  ~~~
  {: title="Curl"}

---

You need to be authenticated and supply a token for all API requests. You will either receive this API token from us directly or be able to generate one within your profile, depending on which API is used. Please refer to the specific API section for instructions on how to get the token for that API.

Nothing will work unless you include the API token
{: .error }

Add the API token to all requests as a query string called 'wstoken'. Send a POST request to https://learn.saylor.org/webservice/rest/server.php. Any function parameters can be appended to the query string.

If you'd like the response to be JSON instead of XML, add "&moodlewsrestformat=json" to the query string.
{: .info}

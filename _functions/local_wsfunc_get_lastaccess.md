---
title: local_wsfunc_get_lastaccess
position: 
type: post
description: Get the last access time for a specified user.
right_code: |
  ~~~ xml
  General structure

  object {
  lastaccess int   //Last access time
  } 
  ~~~
  {: title="Response Structure" }

  ~~~ xml
  <?xml version="1.0" encoding="UTF-8" ?>
  <RESPONSE>
      <SINGLE>
          <KEY name="lastaccess">
              <VALUE>int</VALUE>
          </KEY>
      </SINGLE>
  </RESPONSE>
  ~~~
  {: title="Response" }

  ~~~ xml
  <?xml version="1.0" encoding="UTF-8"?>
  <EXCEPTION class="invalid_parameter_exception">
      <MESSAGE>Invalid parameter value detected</MESSAGE>
      <DEBUGINFO></DEBUGINFO>
  </EXCEPTION>
  ~~~
  {: title="Error" }

---
userid (Default to "0")
: User ID to check the last access of.

~~~
General structure

int  Default to "0" //User ID to check last access.
~~~
{: title="userid" }

The last access time is returned as an integer representing a Unix timestamp. You may want to convert the timestamp to a localized date format before viewing.
{: .success}
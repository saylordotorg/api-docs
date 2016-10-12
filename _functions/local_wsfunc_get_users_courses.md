---
title: local_wsfunc_get_users_courses
position: 
type: post
description: Get list of courses user is enrolled in (only active enrolments are returned).
right_code: |
  ~~~ xml
  General structure

  list of ( 
  object {
  id int   //id of course
  shortname string   //short name of course
  fullname string   //long name of course
  enrolledusercount int   //Number of enrolled users in this course
  idnumber string   //id number of course
  visible int   //1 means visible, 0 means hidden course
  summary string  Optional //summary
  summaryformat int  Optional //summary format (1 = HTML, 0 = MOODLE, 2 = PLAIN or 4 = MARKDOWN)
  format string  Optional //course format: weeks, topics, social, site
  showgrades int  Optional //true if grades are shown, otherwise false
  lang string  Optional //forced course language
  enablecompletion int  Optional //true if completion is enabled, otherwise false
  } 
  )
  ~~~
  {: title="Response Structure"}

  ~~~ xml
  <?xml version="1.0" encoding="UTF-8" ?>
  <RESPONSE>
      <MULTIPLE>
          <SINGLE>
              <KEY name="id">
                  <VALUE>int</VALUE>
              </KEY>
              <KEY name="shortname">
                  <VALUE>string</VALUE>
              </KEY>
              <KEY name="fullname">
                  <VALUE>string</VALUE>
              </KEY>
              <KEY name="enrolledusercount">
                  <VALUE>int</VALUE>
              </KEY>
              <KEY name="idnumber">
                  <VALUE>string</VALUE>
              </KEY>
              <KEY name="visible">
                  <VALUE>int</VALUE>
              </KEY>
              <KEY name="summary">
                  <VALUE>string</VALUE>
              </KEY>
              <KEY name="summaryformat">
                  <VALUE>int</VALUE>
              </KEY>
              <KEY name="format">
                  <VALUE>string</VALUE>
              </KEY>
              <KEY name="showgrades">
                  <VALUE>int</VALUE>
              </KEY>
              <KEY name="lang">
                  <VALUE>string</VALUE>
              </KEY>
              <KEY name="enablecompletion">
                  <VALUE>int</VALUE>
              </KEY>
          </SINGLE>
      </MULTIPLE>
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
userid (Required)
: userid

~~~
General structure

int   //user id
~~~
{: title="userid" }

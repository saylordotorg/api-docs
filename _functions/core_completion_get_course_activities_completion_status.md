---
title: core_completion_get_course_activities_completion_status
position:
type: post
description: Return the activities completion status for a user in a course.
right_code: |
  ~~~ xml
  General structure

  object {
  statuses   //List of activities status
  list of ( 
    //Activity
  object {
  cmid int   //comment ID
  modname string   //activity module name
  instance int   //instance ID
  state int   //completion state value:
                                                                      0 means incomplete, 1 complete,
                                                                      2 complete pass, 3 complete fail
  timecompleted int   //timestamp for completed activity
  tracking int   //type of tracking:
                                                                      0 means none, 1 manual, 2 automatic
  } 
  )warnings  Optional //list of warnings
  list of ( 
    //warning
  object {
  item string  Optional //item
  itemid int  Optional //item id
  warningcode string   //the warning code can be used by the client app to implement specific behaviour
  message string   //untranslated english message to explain the warning
  } 
  )} 
  ~~~
  {: title="Response Structure"}

  ~~~ xml
  <?xml version="1.0" encoding="UTF-8" ?>
  <RESPONSE>
      <SINGLE>
          <KEY name="statuses">
              <MULTIPLE>
                  <SINGLE>
                      <KEY name="cmid">
                          <VALUE>int</VALUE>
                      </KEY>
                      <KEY name="modname">
                          <VALUE>string</VALUE>
                      </KEY>
                      <KEY name="instance">
                          <VALUE>int</VALUE>
                      </KEY>
                      <KEY name="state">
                          <VALUE>int</VALUE>
                      </KEY>
                      <KEY name="timecompleted">
                          <VALUE>int</VALUE>
                      </KEY>
                      <KEY name="tracking">
                          <VALUE>int</VALUE>
                      </KEY>
                  </SINGLE>
              </MULTIPLE>
          </KEY>
          <KEY name="warnings">
              <MULTIPLE>
                  <SINGLE>
                      <KEY name="item">
                          <VALUE>string</VALUE>
                      </KEY>
                      <KEY name="itemid">
                          <VALUE>int</VALUE>
                      </KEY>
                      <KEY name="warningcode">
                          <VALUE>string</VALUE>
                      </KEY>
                      <KEY name="message">
                          <VALUE>string</VALUE>
                      </KEY>
                  </SINGLE>
              </MULTIPLE>
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
courseid (Required)
: Course ID

userid (Required)
: User's ID

~~~
General structure

int   //Course ID
~~~
{: title="courseid" }

~~~
General structure

int   //User ID
~~~
{: title="userid"}

This function will return the completion status for all activities for the specified user in the specified course.

The 'timecompleted' field that is returned for the activities can be used to determine a user's progress through the course.
{: .info}

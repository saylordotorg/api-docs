---
title: core_completion_get_course_completion_status
position:
type: post
description: Returns course completion status.
right_code: |
  ~~~ xml
  General structure

    //Course completion status
  object {
  completionstatus   //Course status
  object {
  completed int   //true if the course is complete, false otherwise
  aggregation int   //aggregation method 1 means all, 2 means any
  completions list of ( 
    //Completions
  object {
  type int   //Completion criteria type
  title string   //Completion criteria Title
  status string   //Completion status (Yes/No) a % or number
  complete int   //Completion status (true/false)
  timecompleted int   //Timestamp for criteria completetion
  details   //details
  object {
  type string   //Type description
  criteria string   //Criteria description
  requirement string   //Requirement description
  status string   //Status description, can be anything
  } 
  } 
  )} 
  warnings  Optional //list of warnings
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
          <KEY name="completionstatus">
              <SINGLE>
                  <KEY name="completed">
                      <VALUE>int</VALUE>
                  </KEY>
                  <KEY name="aggregation">
                      <VALUE>int</VALUE>
                  </KEY>
                  <KEY name="completions">
                      <MULTIPLE>
                          <SINGLE>
                              <KEY name="type">
                                  <VALUE>int</VALUE>
                              </KEY>
                              <KEY name="title">
                                  <VALUE>string</VALUE>
                              </KEY>
                              <KEY name="status">
                                  <VALUE>string</VALUE>
                              </KEY>
                              <KEY name="complete">
                                  <VALUE>int</VALUE>
                              </KEY>
                              <KEY name="timecompleted">
                                  <VALUE>int</VALUE>
                              </KEY>
                              <KEY name="details">
                                  <SINGLE>
                                      <KEY name="type">
                                          <VALUE>string</VALUE>
                                      </KEY>
                                      <KEY name="criteria">
                                          <VALUE>string</VALUE>
                                      </KEY>
                                      <KEY name="requirement">
                                          <VALUE>string</VALUE>
                                      </KEY>
                                      <KEY name="status">
                                          <VALUE>string</VALUE>
                                      </KEY>
                                  </SINGLE>
                              </KEY>
                          </SINGLE>
                      </MULTIPLE>
                  </KEY>
              </SINGLE>
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

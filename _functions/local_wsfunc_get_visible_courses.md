---
title: local_wsfunc_get_visible_courses
position: 
type: post
description: Return courses visible to a user.
right_code: |
  ~~~ xml
  General structure

  object {
  courses list of ( 
    //information about one course
  object {
  id int   //course id
  category int   //category id
  shortname string   //course shortname
  fullname string   //course fullname
  startdate string  Optional //course startdate
  summary string  Optional //course summary
  } 
  )} 
  ~~~
  {: title="Response Structure"}

  ~~~ xml
  <?xml version="1.0" encoding="UTF-8" ?>
  <RESPONSE>
      <SINGLE>
          <KEY name="courses">
              <MULTIPLE>
                  <SINGLE>
                      <KEY name="id">
                          <VALUE>int</VALUE>
                      </KEY>
                      <KEY name="category">
                          <VALUE>int</VALUE>
                      </KEY>
                      <KEY name="shortname">
                          <VALUE>string</VALUE>
                      </KEY>
                      <KEY name="fullname">
                          <VALUE>string</VALUE>
                      </KEY>
                      <KEY name="startdate">
                          <VALUE>string</VALUE>
                      </KEY>
                      <KEY name="summary">
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
cat (Default to "0")
: Category ID: Get visible courses in the category. (Note: This is recursive and will get courses in sub-categories)

~~~
General structure

int  Default to "0" //Category ID: Get visible courses in the category. (Note: This is recursive and will get courses in sub-categories)
~~~
{: title="cat" }

This function returns a list of courses that can be taken by students and corresponding course information such as course id number, the fullname of the course, and a course summary.

All courses fall under the '0' category, so it is ok to leave the value of the cat parameter as the default to see all courses.
{: .success}

---
title: local_wsfunc_get_grades
position: 
type: post
description: Return student course total grade and grades for activities.
right_code: |
  ~~~ xml
  General structure

  object {
  items list of ( 
  object {
  activityid string   //The ID of the activity or "course" for the course grade item
  itemnumber int   //Will be 0 unless the module has multiple grades
  scaleid int   //The ID of the custom scale or 0
  name string   //The module name
  grademin double   //Minimum grade
  grademax double   //Maximum grade
  gradepass double   //The passing grade threshold
  locked int   //0 means not locked, > 1 is a date to lock until
  hidden int   //0 means not hidden, > 1 is a date to hide until
  grades list of ( 
  object {
  userid int   //Student ID
  grade double   //Student grade
  locked int   //0 means not locked, > 1 is a date to lock until
  hidden int   //0 means not hidden, 1 hidden, > 1 is a date to hide until
  overridden int   //0 means not overridden, > 1 means overridden
  feedback string   //Feedback from the grader
  feedbackformat int   //The format of the feedback
  usermodified int   //The ID of the last user to modify this student grade
  datesubmitted int   //A timestamp indicating when the student submitted the activity
  dategraded int   //A timestamp indicating when the assignment was grades
  str_grade string   //A string representation of the grade
  str_long_grade string   //A nicely formatted string representation of the grade
  str_feedback string   //A formatted string representation of the feedback from the grader
  } 
  )} 
  )outcomes  Optional //An array of outcomes associated with the grade items
  list of ( 
  object {
  activityid string   //The ID of the activity or "course" for the course grade item
  itemnumber int   //Will be 0 unless the module has multiple grades
  scaleid int   //The ID of the custom scale or 0
  name string   //The module name
  locked int   //0 means not locked, > 1 is a date to lock until
  hidden int   //0 means not hidden, > 1 is a date to hide until
  grades list of ( 
  object {
  userid int   //Student ID
  grade double   //Student grade
  locked int   //0 means not locked, > 1 is a date to lock until
  hidden int   //0 means not hidden, 1 hidden, > 1 is a date to hide until
  feedback string   //Feedback from the grader
  feedbackformat int   //The feedback format
  usermodified int   //The ID of the last user to modify this student grade
  str_grade string   //A string representation of the grade
  str_feedback string   //A formatted string representation of the feedback from the grader
  } 
  )} 
  )} 
  ~~~
  {: title="Response Structure"}

  ~~~ xml
  <?xml version="1.0" encoding="UTF-8" ?>
  <RESPONSE>
      <SINGLE>
          <KEY name="items">
              <MULTIPLE>
                  <SINGLE>
                      <KEY name="activityid">
                          <VALUE>string</VALUE>
                      </KEY>
                      <KEY name="itemnumber">
                          <VALUE>int</VALUE>
                      </KEY>
                      <KEY name="scaleid">
                          <VALUE>int</VALUE>
                      </KEY>
                      <KEY name="name">
                          <VALUE>string</VALUE>
                      </KEY>
                      <KEY name="grademin">
                          <VALUE>double</VALUE>
                      </KEY>
                      <KEY name="grademax">
                          <VALUE>double</VALUE>
                      </KEY>
                      <KEY name="gradepass">
                          <VALUE>double</VALUE>
                      </KEY>
                      <KEY name="locked">
                          <VALUE>int</VALUE>
                      </KEY>
                      <KEY name="hidden">
                          <VALUE>int</VALUE>
                      </KEY>
                      <KEY name="grades">
                          <MULTIPLE>
                              <SINGLE>
                                  <KEY name="userid">
                                      <VALUE>int</VALUE>
                                  </KEY>
                                  <KEY name="grade">
                                      <VALUE>double</VALUE>
                                  </KEY>
                                  <KEY name="locked">
                                      <VALUE>int</VALUE>
                                  </KEY>
                                  <KEY name="hidden">
                                      <VALUE>int</VALUE>
                                  </KEY>
                                  <KEY name="overridden">
                                      <VALUE>int</VALUE>
                                  </KEY>
                                  <KEY name="feedback">
                                      <VALUE>string</VALUE>
                                  </KEY>
                                  <KEY name="feedbackformat">
                                      <VALUE>int</VALUE>
                                  </KEY>
                                  <KEY name="usermodified">
                                      <VALUE>int</VALUE>
                                  </KEY>
                                  <KEY name="datesubmitted">
                                      <VALUE>int</VALUE>
                                  </KEY>
                                  <KEY name="dategraded">
                                      <VALUE>int</VALUE>
                                  </KEY>
                                  <KEY name="str_grade">
                                      <VALUE>string</VALUE>
                                  </KEY>
                                  <KEY name="str_long_grade">
                                      <VALUE>string</VALUE>
                                  </KEY>
                                  <KEY name="str_feedback">
                                      <VALUE>string</VALUE>
                                  </KEY>
                              </SINGLE>
                          </MULTIPLE>
                      </KEY>
                  </SINGLE>
              </MULTIPLE>
          </KEY>
          <KEY name="outcomes">
              <MULTIPLE>
                  <SINGLE>
                      <KEY name="activityid">
                          <VALUE>string</VALUE>
                      </KEY>
                      <KEY name="itemnumber">
                          <VALUE>int</VALUE>
                      </KEY>
                      <KEY name="scaleid">
                          <VALUE>int</VALUE>
                      </KEY>
                      <KEY name="name">
                          <VALUE>string</VALUE>
                      </KEY>
                      <KEY name="locked">
                          <VALUE>int</VALUE>
                      </KEY>
                      <KEY name="hidden">
                          <VALUE>int</VALUE>
                      </KEY>
                      <KEY name="grades">
                          <MULTIPLE>
                              <SINGLE>
                                  <KEY name="userid">
                                      <VALUE>int</VALUE>
                                  </KEY>
                                  <KEY name="grade">
                                      <VALUE>double</VALUE>
                                  </KEY>
                                  <KEY name="locked">
                                      <VALUE>int</VALUE>
                                  </KEY>
                                  <KEY name="hidden">
                                      <VALUE>int</VALUE>
                                  </KEY>
                                  <KEY name="feedback">
                                      <VALUE>string</VALUE>
                                  </KEY>
                                  <KEY name="feedbackformat">
                                      <VALUE>int</VALUE>
                                  </KEY>
                                  <KEY name="usermodified">
                                      <VALUE>int</VALUE>
                                  </KEY>
                                  <KEY name="str_grade">
                                      <VALUE>string</VALUE>
                                  </KEY>
                                  <KEY name="str_feedback">
                                      <VALUE>string</VALUE>
                                  </KEY>
                              </SINGLE>
                          </MULTIPLE>
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
: id of course

component (Default to "")
: A component, for example mod_forum or mod_quiz

activityid (Default to "null")
: The activity ID

userids (Default to "Array ( ) ")
: An array of user IDs, leave empty to just retrieve grade item information

~~~
General structure

int   //id of course
~~~
{: title="courseid" }

~~~
General structure

string  Default to "" //A component, for example mod_forum or mod_quiz
~~~
{: title="component" }

~~~
General structure

int  Default to "null" //The activity ID
~~~
{: title="activityid"}

~~~
General structure

 Default to "Array()" //An array of user IDs, leave empty to just retrieve grade item information
list of ( 
int   //user ID
)
~~~
{: title="userids"}

This function returns grade information for a specific course or activity in a course. 

If no activity ID is specified, grades are returned for the overall course and all activities within that course.
{: .success}

This function returns a "date_submitted" field which can be used to determine the last activity completed within a course and a user's progress.
{: .info}

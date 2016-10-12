---
title: core_user_get_users
position:
type: post
description: Search for users matching the parameters.
right_code: |
  ~~~ xml
  General structure

  object {
  users list of ( 
  object {
  id int   //ID of the user
  username string  Optional //The username
  firstname string  Optional //The first name(s) of the user
  lastname string  Optional //The family name of the user
  fullname string   //The fullname of the user
  email string  Optional //An email address - allow email as root@localhost
  address string  Optional //Postal address
  phone1 string  Optional //Phone 1
  phone2 string  Optional //Phone 2
  icq string  Optional //icq number
  skype string  Optional //skype id
  yahoo string  Optional //yahoo id
  aim string  Optional //aim id
  msn string  Optional //msn number
  department string  Optional //department
  institution string  Optional //institution
  idnumber string  Optional //An arbitrary ID code number perhaps from the institution
  interests string  Optional //user interests (separated by commas)
  firstaccess int  Optional //first access to the site (0 if never)
  lastaccess int  Optional //last access to the site (0 if never)
  auth string  Optional //Auth plugins include manual, ldap, imap, etc
  confirmed int  Optional //Active user: 1 if confirmed, 0 otherwise
  lang string  Optional //Language code such as "en", must exist on server
  calendartype string  Optional //Calendar type such as "gregorian", must exist on server
  theme string  Optional //Theme name such as "standard", must exist on server
  timezone string  Optional //Timezone code such as Australia/Perth, or 99 for default
  mailformat int  Optional //Mail format code is 0 for plain text, 1 for HTML etc
  description string  Optional //User profile description
  descriptionformat int  Optional //int format (1 = HTML, 0 = MOODLE, 2 = PLAIN or 4 = MARKDOWN)
  city string  Optional //Home city of the user
  url string  Optional //URL of the user
  country string  Optional //Home country code of the user, such as AU or CZ
  profileimageurlsmall string   //User image profile URL - small version
  profileimageurl string   //User image profile URL - big version
  customfields  Optional //User custom fields (also known as user profile fields)
  list of ( 
  object {
  type string   //The type of the custom field - text field, checkbox...
  value string   //The value of the custom field
  name string   //The name of the custom field
  shortname string   //The shortname of the custom field - to be able to build the field class in the code
  } 
  )preferences  Optional //Users preferences
  list of ( 
  object {
  name string   //The name of the preferences
  value string   //The value of the custom field
  } 
  )} 
  )warnings  Optional //list of warnings
  list of ( 
    //warning
  object {
  item string  Optional //always set to 'key'
  itemid int  Optional //faulty key name
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
          <KEY name="users">
              <MULTIPLE>
                  <SINGLE>
                      <KEY name="id">
                          <VALUE>int</VALUE>
                      </KEY>
                      <KEY name="username">
                          <VALUE>string</VALUE>
                      </KEY>
                      <KEY name="firstname">
                          <VALUE>string</VALUE>
                      </KEY>
                      <KEY name="lastname">
                          <VALUE>string</VALUE>
                      </KEY>
                      <KEY name="fullname">
                          <VALUE>string</VALUE>
                      </KEY>
                      <KEY name="email">
                          <VALUE>string</VALUE>
                      </KEY>
                      <KEY name="address">
                          <VALUE>string</VALUE>
                      </KEY>
                      <KEY name="phone1">
                          <VALUE>string</VALUE>
                      </KEY>
                      <KEY name="phone2">
                          <VALUE>string</VALUE>
                      </KEY>
                      <KEY name="icq">
                          <VALUE>string</VALUE>
                      </KEY>
                      <KEY name="skype">
                          <VALUE>string</VALUE>
                      </KEY>
                      <KEY name="yahoo">
                          <VALUE>string</VALUE>
                      </KEY>
                      <KEY name="aim">
                          <VALUE>string</VALUE>
                      </KEY>
                      <KEY name="msn">
                          <VALUE>string</VALUE>
                      </KEY>
                      <KEY name="department">
                          <VALUE>string</VALUE>
                      </KEY>
                      <KEY name="institution">
                          <VALUE>string</VALUE>
                      </KEY>
                      <KEY name="idnumber">
                          <VALUE>string</VALUE>
                      </KEY>
                      <KEY name="interests">
                          <VALUE>string</VALUE>
                      </KEY>
                      <KEY name="firstaccess">
                          <VALUE>int</VALUE>
                      </KEY>
                      <KEY name="lastaccess">
                          <VALUE>int</VALUE>
                      </KEY>
                      <KEY name="auth">
                          <VALUE>string</VALUE>
                      </KEY>
                      <KEY name="confirmed">
                          <VALUE>int</VALUE>
                      </KEY>
                      <KEY name="lang">
                          <VALUE>string</VALUE>
                      </KEY>
                      <KEY name="calendartype">
                          <VALUE>string</VALUE>
                      </KEY>
                      <KEY name="theme">
                          <VALUE>string</VALUE>
                      </KEY>
                      <KEY name="timezone">
                          <VALUE>string</VALUE>
                      </KEY>
                      <KEY name="mailformat">
                          <VALUE>int</VALUE>
                      </KEY>
                      <KEY name="description">
                          <VALUE>string</VALUE>
                      </KEY>
                      <KEY name="descriptionformat">
                          <VALUE>int</VALUE>
                      </KEY>
                      <KEY name="city">
                          <VALUE>string</VALUE>
                      </KEY>
                      <KEY name="url">
                          <VALUE>string</VALUE>
                      </KEY>
                      <KEY name="country">
                          <VALUE>string</VALUE>
                      </KEY>
                      <KEY name="profileimageurlsmall">
                          <VALUE>string</VALUE>
                      </KEY>
                      <KEY name="profileimageurl">
                          <VALUE>string</VALUE>
                      </KEY>
                      <KEY name="customfields">
                          <MULTIPLE>
                              <SINGLE>
                                  <KEY name="type">
                                      <VALUE>string</VALUE>
                                  </KEY>
                                  <KEY name="value">
                                      <VALUE>string</VALUE>
                                  </KEY>
                                  <KEY name="name">
                                      <VALUE>string</VALUE>
                                  </KEY>
                                  <KEY name="shortname">
                                      <VALUE>string</VALUE>
                                  </KEY>
                              </SINGLE>
                          </MULTIPLE>
                      </KEY>
                      <KEY name="preferences">
                          <MULTIPLE>
                              <SINGLE>
                                  <KEY name="name">
                                      <VALUE>string</VALUE>
                                  </KEY>
                                  <KEY name="value">
                                      <VALUE>string</VALUE>
                                  </KEY>
                              </SINGLE>
                          </MULTIPLE>
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
criteria (Required)
: the key/value pairs to be considered in user search. Values can not be empty. Specify different keys only once (fullname => 'user1', auth => 'manual', ...) - key occurences are forbidden. The search is executed with AND operator on the criterias. Invalid criterias (keys) are ignored, the search is still executed on the valid criterias. You can search without criteria, but the function is not designed for it. It could very slow or timeout. The function is designed to search some specific users.

~~~
General structure

  //the key/value pairs to be considered in user search. Values can not be empty.
                        Specify different keys only once (fullname => 'user1', auth => 'manual', ...) -
                        key occurences are forbidden.
                        The search is executed with AND operator on the criterias. Invalid criterias (keys) are ignored,
                        the search is still executed on the valid criterias.
                        You can search without criteria, but the function is not designed for it.
                        It could very slow or timeout. The function is designed to search some specific users.
list of ( 
object {
key string   //the user column to search, expected keys (value format) are:
                                "id" (int) matching user id,
                                "lastname" (string) user last name (Note: you can use % for searching but it may be considerably slower!),
                                "firstname" (string) user first name (Note: you can use % for searching but it may be considerably slower!),
                                "idnumber" (string) matching user idnumber,
                                "username" (string) matching user username,
                                "email" (string) user email (Note: you can use % for searching but it may be considerably slower!),
                                "auth" (string) matching user auth plugin
value string   //the value to search
} 
)
~~~
{: title="criteria" }

You can search for students in your cohort by searching for email addresses matching your cohorts using the % operator (e.g. '%saylor.org').
{: .info}

Be sure to use a domain with the search (%) operator. Bad things happen if just searching email addresses with '%'.
{: .error}
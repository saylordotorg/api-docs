---
title: Program Partner
position: 1.1
description: API for program partners to access information about their students.
apifunctions:
 - core_completion_get_course_activities_completion_status
 - core_completion_get_course_completion_status
 - core_user_get_users
 - core_user_get_users_by_field
 - local_wsfunc_get_grades
 - local_wsfunc_get_lastaccess
 - local_wsfunc_get_visible_courses
right_code: |
---
This API service offers information for program partners to access information about their students - and only students present within their cohort.


<h6>Functions</h6><hr>
<ul>
{% for apifunction in page.apifunctions %}
	<li><a href='{{ site.baseurl}}/#functions{{apifunction}}'>{{apifunction}}</a></li>
{% endfor %}
</ul>

If you are a program partner, Saylor Academy will create an access token for you and send you the access token and cohort ID.
{: .info}



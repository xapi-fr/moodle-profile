# Moodle Profile: Assessment Path Statements

---

- [Supported Statements](#statements)
- [Common Rules for Attempts](#attempt-common-rules)
- [Common Rules for SCOs](#sco-common-rules)
- [Navigated-In Module](#nav-in-module)


<a name="statements"></a>
## Supported Statements

Assessment Path supports the following SCORM Lite statements:
- Launched Attempt
- Initialized Attempt
- Completed Attempt
- Passed / Failed Attempt
- Terminated Attempt
- Passed/Failed SCO (Learner)
- Passed/Failed SCO (Instructor)


<a name="attempt-common-rules"></a>
## Common Rules for Attempts

SCORM Lite rules apply, except the following:

- The `context.contextActivities.parent` property MUST include the Assessment Path test.
- The `context.contextActivities.grouping` property MUST include the Assessment Path step.
- The `context.contextActivities.grouping` property MUST include the Assessment Path activity.


<a name="sco-common-rules"></a>
## Common Rules for SCOs

SCORM Lite rules apply, except the following:

- The `object` property MUST be the Assessment Path test.
- The `context.contextActivities.parent` property MUST include the Assessment Path step.
- The `context.contextActivities.grouping` property MUST include the Assessment Path activity.



<a name="nav-in-module"></a>
## Navigated-In Module

This Statement is generated from the `\mod_assessmentpath\event\course_module_viewed` event 
and follows the same rules than other modules (see [navigation events](events_nav#nav-in-module)).



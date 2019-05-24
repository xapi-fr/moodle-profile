# Moodle Profile: Statements

---

- [Granularity levels](#granularity)
- [Common rules](#common-rules)
- [Navigation statements](#nav)
- [H5P statements](#hvp)


<a name="granularity"></a>
## Granularity levels

- The `outside-learning-unit` granularity level covers the Moodle *courses* events.
- The `learning-unit` granularity level covers the Moodle *modules* events, in other words Moodle *resources* and *activities* events.
- The `inside-learning-unit` granularity level covers all the events which are internal to the Moodle *modules*.

<a name="common-rules"></a>
## Common rules

- All VLE profile rules apply.
- All lang string keys (e.g. `en-US`) MUST be defined according to system and course settings.
- The `context.platform` property MUST always be `Moodle`.
- Statements with a `learning-unit` granularity level MUST include a Moodle *course* in the `context.contextActivities.parent` property.
- Statements with a `inside-learning-unit` granularity level MUST include a Moodle *module* in the `context.contextActivities.parent` property.
- Statements with a `inside-learning-unit` granularity level MUST include a Moodle *course* in the `context.contextActivities.grouping` property.


<a name="nav"></a>
## Navigation statements

- [Logged-In](nav#logged-in)
- [Logged-Out](nav#logged-out)
- [Navigated-In Course](nav#nav-in-course)
- [Navigated-In Course Category](nav#nav-in-course-category)
- [Navigated-In Module](nav#nav-in-module)


<a name="comp"></a>
## Completion statements

- [Completed Course](comp#completed-course)


<a name="hvp"></a>
## H5P statements

- [Completed Quiz](hvp#completed-quiz)
- [Answered Quiz Question](hvp#answered-quiz-question)
- [Answered Single Question](hvp#answered-single-question)
- [Course Module Viewed](hvp#course-module-viewed)

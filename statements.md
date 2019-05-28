# Moodle Profile: Statements

---

- [Granularity levels](#granularity)
- [Common rules](#common-rules)


<a name="granularity"></a>
## Granularity levels

- The `outside-learning-unit` granularity level covers the Moodle *courses* and *categories* events.
- The `learning-unit` granularity level covers the Moodle *modules* events, in other words Moodle *resources* and *activities* events.
- The `inside-learning-unit` granularity level covers all the events which are internal to the Moodle *modules*.

<a name="common-rules"></a>
## Common rules

- All VLE profile rules apply.
- All lang string keys (e.g. `en-US`) MUST be defined according to system and course settings.
- The `context.platform` property MUST always be `Moodle`.
- Statements with a `learning-unit` granularity level MUST include a Moodle *course* in the `context.contextActivities.parent` property.
- Statements with a `inside-learning-unit` granularity level MUST include a Moodle *module* in the `context.contextActivities.parent` property, and a Moodle *course* in the `context.contextActivities.grouping` property.



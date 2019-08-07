# Moodle / VLE Profile: Statements

---

- [Granularity levels](#granularity)
- [Common rules](#common-rules)
- [System](#system)
- [Outside Learning Unit](#outside-learning-unit)
- [Learning Unit](#learning-unit)
- [Inside Learning Unit](#inside-learning-unit)


<a name="granularity"></a>
## Granularity levels

- **System:** statements whose object is the platform itself (e.g. `logged-in`, `logged-out` statements).
- **Outside Learning Unit:** statements whose object is an aggregation of learning activities (e.g. Moodle `course` and `course category`).
- **Learning Unit:** statements whose object is an atomic learning activity, usually subject to be completed, passed or failed (e.g. Moodle `course module`).
- **Inside Learning Unit:** statements which reflect something that happens inside a learning unit (e.g. `question` inside a Quiz).


<a name="common-rules"></a>
## Common rules

- The `verb.display` property MAY be omitted.
- The `type` property MUST be defined for all the activities of a statement.
- All known activity properties SHOULD be defined when the activity is the `object` of the statement.
- Optional activity properties SHOULD be omitted when the activity is in the `contextActivities` of the statement.
- The `platform-event` extension of the `context` MUST define the platform source event.
- The `timestamp` property MUST be defined.
- All lang string keys (e.g. `en-US`) MUST be defined according to system and course settings.


<a name="system"></a>
## System

- The `object.definition.type` property MUST be `http://vocab.xapi.fr/activities/system`. 
- The `object.definition.id` property MUST be the platform IRI. 


<a name="outside-learning-unit"></a>
## Outside Learning Unit

- The `platform-concept` extension of the `object` MUST be defined. 
- The `context.contextActivities.grouping` property MUST include the system activity. 


<a name="learning-unit"></a>
## Learning Unit

- The `platform-concept` extension of the `object` MUST be defined. 
- The `concept-family` extension of the `object` MUST be defined.
- The `standard` extension of the `object` MAY be defined if the activity conforms to a standard (e.g. `scorm`, `lti`).
- The `context.contextActivities.parent` property MUST define the Moodle course which contains the learning unit.  
- The `context.contextActivities.grouping` property MUST include the system activity. 
- The `context.contextActivities.category` property MUST include a granularity activity with `type` set to `http://vocab.xapi.fr/activities/granularity-level` and `id` set to `http://vocab.xapi.fr/categories/learning-unit`.


<a name="inside-learning-unit"></a>
## Inside Learning Unit

- The `context.contextActivities.parent` property MUST define the direct parent activity in which the event occurs. It MAY be a Moodle course module, or a sub-activity of the course module.
- The `context.contextActivities.grouping` property MUST include the system activity.
- The `context.contextActivities.grouping` property MUST include the Moodle course which contains the learning unit.
- The `context.contextActivities.grouping` property MUST include the Moodle course module if it not already included in the `context.contextActivities.parent` property. 
- The `context.contextActivities.category` property MUST include a granularity activity with `type` set to `http://vocab.xapi.fr/activities/granularity-level` and `id` set to `http://vocab.xapi.fr/categories/inside-learning-unit`.

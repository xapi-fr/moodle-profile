# Moodle Profile: Identification

---

- [Agents](#agents)
- [Activities](#activities)
- [Profil](#profile)


<a name="agents"></a>
## Agents

- As specified by the VLE profile, the `account` format is used to identify the agents.


<a name="activities"></a>
## Activities

Most of the time, activities identification conforms with the `http://platform-iri/xapi/activities/xxx/yyy` schema, where:
- `http://platform-iri` is the platform IRI.
- `xxx` is the Moodle table matching with the activity type (e.g. `course`, `scorm`).
- `yyy` is an activity identifier (e.g. a generated UUID).

Examples:
- Course: `http://xapi.moodle.test/xapi/activities/course/1fae9d58-6bc7-42ec-ad9f-f9633d102fef`
- SCORM activity: `http://xapi.moodle.test/xapi/activities/scorm/29b3a311-f4a5-4beb-8611-9e759767b37e`

Regarding activities with an `inside-learning-unit` granularity level, their IRI is based on their parent activity, extended with a sub-level of identification.

Examples:
- Quiz activity: `http://xapi.moodle.test/xapi/activities/quiz/29b3a311-f4a5-4beb-8611-9e759767b37e`.
- Question inside the Quiz activity: `http://xapi.moodle.test/xapi/activities/quiz/29b3a311-f4a5-4beb-8611-9e759767b37e/question/1fae9d58-6bc7-42ec-ad9f-f9633d102fef`.


<a name="profile"></a>
## Moodle Profile

As the Moodle profile is a VLE profile, it is identified with `http://vocab.xapi.fr/categories/vle-profile`.

Furthermore, the `context.platform` property MUST always be `Moodle`.





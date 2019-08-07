# Moodle / VLE Profile: Identification

---

- [Agents](#agents)
- [Activities](#activities)
- [Profil](#profile)


<a name="agents"></a>
## Agents

- Agents identification MUST be based on the `account` format. 
- The `account.homePage` MUST be a stable platform IRI which is not subject to change, even if the platform hosting domain changes.
- The `account.name` MAY be the username used to authenticate the user on the platform, but only if this username can't be changed.
- The `account.name` SHOULD be an anonymous identifier (e.g. a UUID) to preserve data privacy. 
- The `name` SHOULD be ommited to preserve data privacy.

``` json
"actor": {
    "objectType": "Agent",
    "account": {
        "homePage": "http://my-vle.com",
        "name": "8be985de-9d4f-331a-8f06-fd4bab2030f7"
    }
}
```


<a name="activities"></a>
## Activities

### Rules

- Activities MUST be identified with a stable and permanent IRI.
- Most activities SHOULD conform with the `<platform-iri>/xapi/activities/<type>/<uuid>` schema.
- The identifier of low level activities MAY extend the identifier of their parent activities.

### Examples

- Course: `http://xapi.moodle.test/xapi/activities/course/1fae9d58-6bc7-42ec-ad9f-f9633d102fef`
- SCORM activity: `http://xapi.moodle.test/xapi/activities/scorm/29b3a311-f4a5-4beb-8611-9e759767b37e`
- SCO inside a SCORM activity: `http://xapi.moodle.test/xapi/activities/scorm/29b3a311-f4a5-4beb-8611-9e759767b37e/sco/1fae9d58-6bc7-42ec-ad9f-f9633d102fef`


<a name="profile"></a>
## Moodle / VLE Profile

- The `context.contextActivities.category` property MUST include a profile activity with the `http://vocab.xapi.fr/categories/vle-profile` identifier.
- The `context.platform` property MUST be set to `Moodle`.





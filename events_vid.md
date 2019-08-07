# Moodle / VLE Profile: Video Statements

---

- [Global rules](#global-rules)
- [Context adaptation](#context)
- [JSON Example](#example)


<a name="global-rules"></a>
## Global rules

- Statements MUST conform with the [xAPI Video Profile](https://liveaspankaj.gitbooks.io/xapi-video-profile/content/).
- The `actor` MUST be replaced by the authenticated user, as defined by the VLE profile.
- The `verb.display` property MAY be removed.
- The `context` MUST be adapted in order to conform with the Moodle / VLE Profile.
- All other elements of the statements MUST be kept without modification.


<a name="context"></a>
## Context adaptation

- The `context.platform` property MUST be set to `Moodle`.
- The `context.contextActivities.parent` property MUST include the Trax Video Moodle activity.
- The `context.contextActivities.grouping` property MUST include the Moodle course, as well as the Moodle instance.
- The `context.contextActivities.category` property MUST include a granularity level set to `inside-learning-unit`.
- The `context.contextActivities.category` property MUST include the xAPI video profile, with its `id`, `type` and `objectType`.


<a name="example"></a>
## JSON Example

```json
{
    "id": "f1f4d68f-50ba-4d0c-94f4-ea2f24636de2",
    "actor": {
        "objectType": "Agent",
        "account": {
            "name": "d0d6cd21-bbea-4179-a7e9-affdea1a1d84",
            "homePage": "http://xapi.moodle.test"
        }
    },
    "verb": {
        "id": "http://adlnet.gov/expapi/verbs/terminated"
    },
    "object": {
        "objectType": "Activity",
        "id": "http://moodle.test/xapi/activities/traxvideo/ab9d2fb0-3081-429f-8bd4-7cedec429af7/items/01",
        "definition": {
            "type": "https://w3id.org/xapi/video/activity-type/video",
            "name": {
                "fr": "Here is the title of the activity..."
            }
        }
    },
    "result": {
        "extensions": {
            "https://w3id.org/xapi/video/extensions/time": 5.111,
            "https://w3id.org/xapi/video/extensions/progress": 0.11,
            "https://w3id.org/xapi/video/extensions/played-segments": "0[.]3.774[,]3.774[.]5.111"
        }
    },
    "context": {
        "contextActivities": {
            "parent": [
                {
                    "objectType": "Activity",
                    "id": "http://moodle.test/xapi/activities/traxvideo/ab9d2fb0-3081-429f-8bd4-7cedec429af7",
                    "definition": {
                        "type": "http://vocab.xapi.fr/activities/resources"
                    }
                }
            ],
            "grouping": [
                {
                    "objectType": "Activity",
                    "id": "http://moodle.test",
                    "definition": {
                        "type": "http://vocab.xapi.fr/activities/system"
                    }
                },
                {
                    "objectType": "Activity",
                    "id": "http://moodle.test/xapi/activities/course/738a5680-b46f-478d-9418-4e4aba7fb79a",
                    "definition": {
                        "type": "http://vocab.xapi.fr/activities/course"
                    }
                }
            ],
            "category": [
                {
                    "objectType": "Activity",
                    "id": "http://vocab.xapi.fr/categories/inside-learning-unit",
                    "definition": {
                        "type": "http://vocab.xapi.fr/activities/granularity-level"
                    }
                },
                {
                    "objectType": "Activity",
                    "id": "https://w3id.org/xapi/video",
                    "definition": {
                        "type": "http://adlnet.gov/expapi/activities/profile"
                    }
                }
            ],
        },
        "platform": "Moodle",
        "extensions": {
            "https://w3id.org/xapi/video/extensions/length": 46.613333,
            "https://w3id.org/xapi/video/extensions/session-id": "7554dd48-e7a7-4757-80db-a02880313066",
            "https://w3id.org/xapi/video/extensions/completion-threshold": "1.0"
        }
    },
    "timestamp": "2018-06-20T16:04:17+08:00"
}
```


# Moodle / VLE Profile: SCORM Statements

---

- [Supported Statements](#statements)
- [Unsupported events](#unsupported-event)
- [Launched SCO](#launched-sco)


<a name="statements"></a>
## Supported Statements

### SCORM Statements
- Launched SCO

### Course Module Statements
- Navigated-In Course Module (on Moodle viewed event)
- Completed Course Module (on Moodle completion event)
- Graded Course Module (on Moodle grading event)


<a name="unsupported-event"></a>
## Unsupported events

Some significant SCORM events are not supported, including **Submitted Raw Score** and **Submitted Status**. 
The main reason is that a separated event is triggered for each SCORM property (`completion_status`, `success_status` and `score`) each time it is submitted. The result is a flow of atomic events which are not relevant taken individually.
A more global approach have been implemented in the [SCORM Lite](events_scormlite) plugin, which offers an alternative to the native SCORM activity, with a wider range of supported events.


<a name="launched-sco"></a>
## Launched SCO

This Statement is generated from the `\mod_scorm\event\sco_launched` Moodle event.

```json
{
    "actor": {
        "objectType": "Agent",
        "account": {
            "name": "d0d6cd21-bbea-4179-a7e9-affdea1a1d84",
            "homePage": "http://xapi.moodle.test"
        }
    },
    "verb": {
        "id": "http://adlnet.gov/expapi/verbs/launched"
    },
    "object": {
        "objectType": "Activity",
        "id": "http://xapi.moodle.com/xapi/activities/scorm/b3192e37-6d57-4a6b-8642-b9259276440d/sco/40DB4D59-4F85-46E7-85B8-52268EFB7EB4",
        "definition": {
            "type": "http://vocab.xapi.fr/activities/content-object",
            "name": {
                "en": "SCORM Presentation"
            },
            "extensions": {
                "http://vocab.xapi.fr/extensions/standard": "scorm"
            }
        }
    },
    "context": {
        "contextActivities": {
            "parent": [
                {
                    "id": "http://xapi.moodle.com/xapi/activities/scorm/21c872e3-e5fc-42ee-8f34-cc45a91ed777",
                    "definition": {
                        "type": "http://vocab.xapi.fr/activities/web-content"
                    }
                }
            ],
            "grouping": [
                {
                    "id": "http://xapi.moodle.com",
                    "definition": {
                        "type": "http://vocab.xapi.fr/activities/system"
                    }
                },
                {
                    "id": "http://xapi.moodle.com/xapi/activities/course/5305a8f7-943f-4647-bc69-74ccd52e9921",
                    "definition": {
                        "type": "http://vocab.xapi.fr/activities/course"
                    }
                }
            ],
            "category": [
                {
                    "id": "http://vocab.xapi.fr/categories/inside-learning-unit",
                    "definition": {
                        "type": "http://vocab.xapi.fr/activities/granularity-level"
                    }
                },
                {
                    "id": "http://vocab.xapi.fr/categories/vle-profile",
                    "definition": {
                        "type": "http://adlnet.gov/expapi/activities/profile"
                    }
                }
            ]
        },
        "platform": "Moodle",
        "extensions": {
            "http://vocab.xapi.fr/extensions/platform-event": "\\mod_scorm\\event\\sco_launched"
        }
    },
    "timestamp": "2019-08-14T17:20:52+02:00"
}
```


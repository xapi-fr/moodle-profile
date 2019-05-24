# Moodle Profile: Completion events

---

- [Completed Course](#completed-course)


<a name="completed-course"></a>
## Completed Course

This Statement is generated from the `\core\event\course_completed` Moodle event.

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
        "id": "http://adlnet.gov/expapi/verbs/completed"
    },
    "object": {
        "objectType": "Activity",
        "id": "http://xapi.moodle.test/xapi/activities/course/ba297687-b1aa-4477-9efd-a782c8fdb90a",
        "definition": {
            "type": "http://vocab.xapi.fr/activities/course",
            "name": {
                "en": "Course 1"
            },
            "description": {
                "en": "Course 1 description"
            },
            "extensions": {
                "http://vocab.xapi.fr/extensions/platform-concept": "course"
            }
        }
    },
    "context": {
        "contextActivities": {
            "grouping": [
                {
                    "objectType": "Activity",
                    "id": "http://xapi.moodle.test",
                    "definition": {
                        "type": "http://vocab.xapi.fr/activities/system"
                    }
                }
            ],            
            "category": [
                {
                    "id": "http://vocab.xapi.fr/categories/vle-profile",
                    "definition": {
                        "type": "http://adlnet.gov/expapi/activities/profile"
                    }
                }
            ]
        },
        "platform": "Moodle"
    },
    "timestamp": "2018-06-20T16:04:17+08:00"
}
```


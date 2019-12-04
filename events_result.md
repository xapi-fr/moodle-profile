# Moodle / VLE Profile: Grading Statements

---

- [Course Module Graded](#module-graded)


<a name="module-graded"></a>
## Course Module Graded


### Generation

This Statement is generated from the `\xxx\event\user_graded` Moodle event when all the following conditions are met:
- The grade item is associated with a *course module*.
- The grade type is *value* or *scale*.
- The raw value of the grade is known.


### Rules

- The `object` property MUST define the Moodle course module.
- The `result.score` property MUST be set, including `min`, `max`, `raw` and `scaled`.
- The `result.success` property MUST be set when it is known.


### Example

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
        "id": "http://vocab.xapi.fr/verbs/graded"
    },
    "object": {
        "objectType": "Activity",
        "id": "http://xapi.moodle.test/xapi/activities/scorm/c1595f9a-4347-404b-9057-51c461fcd1b7",
        "definition": {
            "type": "http://vocab.xapi.fr/activities/web-content",
            "name": {
                "en": "Content 1"
            },
            "description": {
                "en": "Content 1 description"
            },
            "extensions": {
                "http://vocab.xapi.fr/extensions/platform-concept": "scorm",
                "http://vocab.xapi.fr/extensions/concept-family": "resource",
                "http://vocab.xapi.fr/extensions/standard": "scorm"
            }
        }
    },
    "result": {
        "score": {
            "max": 100,
            "min": 0,
            "raw": 75,
            "scaled": 0.75
        },
        "success": true
    },
    "context": {
        "contextActivities": {
            "parent": [
                {
                    "id": "http://xapi.moodle.test/xapi/activities/course/ba297687-b1aa-4477-9efd-a782c8fdb90a",
                    "definition": {
                        "type": "http://vocab.xapi.fr/activities/course"
                    }
                }
            ],
            "grouping": [
                {
                    "id": "http://xapi.moodle.test",
                    "definition": {
                        "type": "http://vocab.xapi.fr/activities/system"
                    }
                }
            ],            
            "category": [
                {
                    "id": "http://vocab.xapi.fr/categories/learning-unit",
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
            "http://vocab.xapi.fr/extensions/platform-event": "\\core\\event\\user_loggedin"
        }
    },
    "timestamp": "2018-06-20T16:04:18+08:00"
}
```



# Moodle Profile: Result Statements

---

- [Common rules](#common-rules)
- [Module Scored](#module-scored)
- [Module Passed](#module-passed)
- [Module Failed](#module-failed)


<a name="common-rules"></a>
## Common rules

- The `result.success` property MUST be set when it is known.
- The `result.score` property MUST be set when it is known, including `min`, `max` and `scaled` when available.


<a name="module-scored"></a>
## Module Scored

This Statement is generated from the `\xxx\event\user_graded` Moodle event when all the following conditions are met:
- The grade item is associated with an activity.
- The grade type is *value* or *scale*.
- The raw value of the grade is known.
- The success status is unknwon (no passing grade defined).

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
        "id": "http://adlnet.gov/expapi/verbs/scored"
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
        }
    },
    "context": {
        "contextActivities": {
            "parent": [
                {
                    "objectType": "Activity",
                    "id": "http://xapi.moodle.test/xapi/activities/course/ba297687-b1aa-4477-9efd-a782c8fdb90a",
                    "definition": {
                        "type": "http://vocab.xapi.fr/activities/course"
                    }
                }
            ],
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
        "platform": "Moodle"
    },
    "timestamp": "2018-06-20T16:04:18+08:00"
}
```

<a name="module-passed"></a>
## Module Passed

This Statement is generated from the `\xxx\event\user_graded` Moodle event when all the following conditions are met:
- The grade item is associated with an activity.
- The grade type is *value* or *scale*.
- The raw value of the grade is known.
- The success status is *true*.

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
        "id": "http://adlnet.gov/expapi/verbs/passed"
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
                    "objectType": "Activity",
                    "id": "http://xapi.moodle.test/xapi/activities/course/ba297687-b1aa-4477-9efd-a782c8fdb90a",
                    "definition": {
                        "type": "http://vocab.xapi.fr/activities/course"
                    }
                }
            ],
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
        "platform": "Moodle"
    },
    "timestamp": "2018-06-20T16:04:18+08:00"
}
```

<a name="module-failed"></a>
## Module Failed

This Statement is generated from the `\xxx\event\user_graded` Moodle event when all the following conditions are met:
- The grade item is associated with an activity.
- The grade type is *value* or *scale*.
- The raw value of the grade is known.
- The success status is *false*.

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
        "id": "http://adlnet.gov/expapi/verbs/failed"
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
            "raw": 25,
            "scaled": 0.25
        },
        "success": false
    },
    "context": {
        "contextActivities": {
            "parent": [
                {
                    "objectType": "Activity",
                    "id": "http://xapi.moodle.test/xapi/activities/course/ba297687-b1aa-4477-9efd-a782c8fdb90a",
                    "definition": {
                        "type": "http://vocab.xapi.fr/activities/course"
                    }
                }
            ],
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
        "platform": "Moodle"
    },
    "timestamp": "2018-06-20T16:04:18+08:00"
}
```

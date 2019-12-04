# Moodle / VLE Profile: Completion Statements

---

- [Common rules](#common-rules)
- [Course Completed](#course-completed)
- [Course Module Completed](#module-completed)
- [Course Module Completion Marked](#module-completion-marked)


<a name="common-rules"></a>
## Common rules

- The `result.completion` property MUST be set to `true`.
- The `result.success` property MUST be set when it is known (module completion with COMPLETE_PASS or COMPLETE_FAIL status).


<a name="course-completed"></a>
## Course Completed

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
    "result": {
        "completion": true
    },
    "context": {
        "contextActivities": {
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
                    "id": "http://vocab.xapi.fr/categories/vle-profile",
                    "definition": {
                        "type": "http://adlnet.gov/expapi/activities/profile"
                    }
                }
            ]
        },
        "platform": "Moodle",
        "extensions": {
            "http://vocab.xapi.fr/extensions/platform-event": "\\core\\event\\course_completed"
        }
    },
    "timestamp": "2018-06-20T16:04:17+08:00"
}
```


<a name="module-completed"></a>
## Course Module Completed

This Statement is generated from the `\xxx\event\course_module_completion_updated` Moodle event when all the following conditions are met:
- The completion is determined automatically.
- The activity is completed (COMPLETE, COMPLETE_PASS or COMPLETE_FAIL status).

### Rules

- The `result.completion` property MUST be defined and `true`.


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
        "completion": true
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
            "http://vocab.xapi.fr/extensions/platform-event": "\\mod_forum\\event\\course_module_completion_updated"
        }
    },
    "timestamp": "2018-06-20T16:04:18+08:00"
}
```


<a name="module-completion-marked"></a>
## Course Module Completion Marked

This Statement is generated from the `\xxx\event\course_module_completion_updated` Moodle event when all the following conditions are met:
- The completion is determined manually by the learner.
- The activity is completed (COMPLETE, COMPLETE_PASS or COMPLETE_FAIL status).

### Rules

- The `result.completion` property MUST be defined.Its value MAY be `true` or `false`.


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
        "id": "http://vocab.xapi.fr/verbs/marked-completion"
    },
    "object": {
        "objectType": "Activity",
        "id": "http://xapi.moodle.test/xapi/activities/resource/c1595f9a-4347-404b-9057-51c461fcd1b7",
        "definition": {
            "type": "http://adlnet.gov/expapi/activities/file",
            "name": {
                "en": "PDF 1"
            },
            "description": {
                "en": "PDF 1 description"
            },
            "extensions": {
                "http://vocab.xapi.fr/extensions/platform-concept": "resource",
                "http://vocab.xapi.fr/extensions/concept-family": "resource"            }
        }
    },
    "result": {
        "completion": false
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
            "http://vocab.xapi.fr/extensions/platform-event": "\\mod_forum\\event\\course_module_completion_updated"
        }
    },
    "timestamp": "2018-06-20T16:04:18+08:00"
}
```

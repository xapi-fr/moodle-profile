# Moodle / VLE Profile: AssessmentPath Statements

---

- [Supported Statements](#statements)
- [Identification Schema](#id)
- [Activity Types](#types)
- [Common Rules for Attempt Statements](#attempt-common-rules)
- [Common Rules for SCO Statements](#sco-common-rules)


<a name="statements"></a>
## Supported Statements

### Attempt Statements
- Launched Attempt
- Initialized Attempt
- Completed Attempt
- Passed / Failed Attempt
- Terminated Attempt

### SCO Statements
- Passed/Failed SCO (obtained by learner)
- Passed/Failed SCO (changed by instructor)

### Activity Statements
- Navigated-In Activity (on Moodle viewed event)
- Completed Activity (on Moodle completion event)
- Scored Activity (on Moodle grading event)


<a name="id"></a>
## Identification Schema

- AssessmentPath activity: `<platform-iri>/xapi/activities/assessmentpath/<uuid>`
- AssessmentPath step: `<platform-iri>/xapi/activities/assessmentpath/<uuid>/step/<step>`
- AssessmentPath test: `<platform-iri>/xapi/activities/assessmentpath/<uuid>/step/<step>/<initial-or-remedial>`
- AssessmentPath SCO: `<platform-iri>/xapi/activities/assessmentpath/<uuid>/step/<step>/<initial-or-remedial>/sco`


<a name="types"></a>
## Activity Types

- AssessmentPath activity: `http://vocab.xapi.fr/activities/web-content`
- AssessmentPath step: `http://vocab.xapi.fr/activities/training-sequence`
- AssessmentPath test: `http://vocab.xapi.fr/activities/quiz`
- AssessmentPath SCO: `http://vocab.xapi.fr/activities/content-object`


<a name="attempt-common-rules"></a>
## Common Rules for Attempt Statements

SCORM Lite rules apply, except the following:

- The `object` property MUST define the content object (SCO).
- The `context.contextActivities.parent` property MUST include the AssessmentPath test.
- The `context.contextActivities.grouping` property MUST include the AssessmentPath step.
- The `context.contextActivities.grouping` property MUST include the AssessmentPath activity.


### Example

```json
{
    "id": "4562cd21-bbea-4179-a7e9-affdea1a1789",
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
        "id": "http://xapi.moodle.test/xapi/activities/assessmentpath/86e15642-5e46-45c2-8fd2-7c88d2e37edf/step/1/initial/sco",
        "definition": {
            "type": "http://vocab.xapi.fr/activities/content-object",
            "extensions": {
                "http://vocab.xapi.fr/extensions/standard": "scorm"
            }
        }
    },
    "context": {
        "contextActivities": {
            "parent": [
                {
                    "id": "http://xapi.moodle.test/xapi/activities/assessmentpath/86e15642-5e46-45c2-8fd2-7c88d2e37edf/step/1/initial",
                    "definition": {
                        "type": "http://vocab.xapi.fr/activities/quiz"
                    }
                }
            ],
            "grouping": [
                {
                    "id": "http://xapi.moodle.test",
                    "definition": {
                        "type": "http://vocab.xapi.fr/activities/system"
                    }
                },
                {
                    "id": "http://xapi.moodle.test/xapi/activities/course/54b9d6f3-c14b-4abf-b613-f5e5fb5ecd40",
                    "definition": {
                        "type": "http://vocab.xapi.fr/activities/course"
                    }
                },
                {
                    "id": "http://xapi.moodle.test/xapi/activities/assessmentpath/86e15642-5e46-45c2-8fd2-7c88d2e37edf",
                    "definition": {
                        "type": "http://vocab.xapi.fr/activities/web-content"
                    }
                },
                {
                    "id": "http://xapi.moodle.test/xapi/activities/assessmentpath/86e15642-5e46-45c2-8fd2-7c88d2e37edf/step/1",
                    "definition": {
                        "type": "http://vocab.xapi.fr/activities/training-sequence"
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
                },
                {
                    "id": "https://w3id.org/xapi/cmi5/context/categories/cmi5",
                    "definition": {
                        "type": "http://adlnet.gov/expapi/activities/profile"
                    }
                }
            ],
        },
        "registration": "54b9d6f3-c14b-4abf-b613-f5e5fb5ecd40",
        "platform": "Moodle",
        "extensions": {
            "http://vocab.xapi.fr/extensions/platform-event": "\\mod_assessmentpath\\event\\attempt_launched",
            "http://id.tincanapi.com/extension/attempt-id": 2,
            "https://w3id.org/xapi/cmi5/context/extensions/sessionid": "7584cd21-bbea-4179-a7e9-affdea1a4444",
            "https://w3id.org/xapi/cmi5/context/extensions/launchmode": "Review",
            "http://vocab.xapi.fr/extensions/launch-method": "OwnWindow",
            "http://vocab.xapi.fr/extensions/learner": {
                "objectType": "Agent",
                "account": {
                    "name": "d0d6cd21-bbea-4179-a7e9-affdea1a1d85",
                    "homePage": "http://xapi.moodle.test"
                }
            }
        }
    },
    "timestamp": "2018-06-20T16:04:17+08:00"
}
```


<a name="sco-common-rules"></a>
## Common Rules for SCO Statements

SCORM Lite rules apply, except the following:

- The `object` property MUST be the AssessmentPath test.
- The `remedial` extension of the `object` MUST be defined. 
- The `context.contextActivities.parent` property MUST include the AssessmentPath step.
- The `context.contextActivities.grouping` property MUST include the AssessmentPath activity.
- The `context.contextActivities.category` property MUST include a granularity level activity with an ID set to `inside-learning-unit`.


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
        "id": "http://adlnet.gov/expapi/verbs/passed"
    },
    "object": {
        "objectType": "Activity",
        "id": "http://xapi.moodle.test/xapi/activities/assessmentpath/86e15642-5e46-45c2-8fd2-7c88d2e37edf/step/1/initial",
        "definition": {
            "type": "http://vocab.xapi.fr/activities/quiz",
            "extensions": {
                "http://vocab.xapi.fr/extensions/remedial": false
            }
        }
    },
    "result": {
        "success": true,
        "score": {
            "max": 100,
            "min": 0,
            "raw": 75,
            "scaled": 0.75
        },
        "duration": "PT64.03S"
    },
    "context": {
        "contextActivities": {
            "parent": [
                {
                    "id": "http://xapi.moodle.test/xapi/activities/assessmentpath/86e15642-5e46-45c2-8fd2-7c88d2e37edf/step/1",
                    "definition": {
                        "type": "http://vocab.xapi.fr/activities/training-sequence"
                    }
                }
            ],
            "grouping": [
                {
                    "id": "http://xapi.moodle.test",
                    "definition": {
                        "type": "http://vocab.xapi.fr/activities/system"
                    }
                },
                {
                    "id": "http://xapi.moodle.test/xapi/activities/course/54b9d6f3-c14b-4abf-b613-f5e5fb5ecd40",
                    "definition": {
                        "type": "http://vocab.xapi.fr/activities/course"
                    }
                },
                {
                    "id": "http://xapi.moodle.test/xapi/activities/assessmentpath/86e15642-5e46-45c2-8fd2-7c88d2e37edf",
                    "definition": {
                        "type": "http://vocab.xapi.fr/activities/web-content"
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
            ],
        },
        "platform": "Moodle",
        "extensions": {
            "http://vocab.xapi.fr/extensions/platform-event": "\\mod_assessmentpath\\event\\sco_result_updated",
            "http://id.tincanapi.com/extension/attempt-id": 2,
            "http://vocab.xapi.fr/extensions/attempts-number": 3,
            "http://vocab.xapi.fr/extensions/max-attempts": 6,
            "https://w3id.org/xapi/cmi5/context/extensions/masteryscore": 50,
            "http://vocab.xapi.fr/extensions/scoring-method": "BestAttempt",
            "http://vocab.xapi.fr/extensions/max-time": "PT1H"
        }
    },
    "timestamp": "2018-06-20T16:04:17+08:00"
}
```




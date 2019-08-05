# Moodle Profile: SCORM Lite Statements

---

- [Common Rules for Attempts](#attempt-common-rules)
- [Launched Attempt](#launched-attempt)
- [Initialized Attempt](#initialized-attempt)
- [Completed Attempt](#completed-attempt)
- [Passed/Failed Attempt](#passed-failed-attempt)
- [Terminated Attempt](#terminated-attempt)
- [Passed/Failed SCO (Learner)](#passed-failed-sco-learner)
- [Passed/Failed SCO (Instructor)](#passed-failed-sco-instructor)
- [Navigated-In Module](#nav-in-module)


<a name="attempt-common-rules"></a>
## Common Rules for Attempts

When the object of the Statement is a SCO, the following rules apply:

- The `id` property MUST be defined (UUID).
- The `object.definition.type` property MUST be `http://adlnet.gov/expapi/activities/lesson`.
- The `context.registration` property MUST be defined (UUID). It MAY use the course UUID as the enrolment in Moodle is managed at the course level.
- The `context.contextActivities.parent` property MUST include the Moodle SCORM Lite activity.
- The `context.contextActivities.category` property MUST include a granularity level set to `inside-learning-unit`.
- The `context.contextActivities.category` property MUST include the CMI5 profile, with its `id` and `type`.
- The `attempt-id` extension of the `context` MUST define the number of the current attempt (starting from 1). 
- The `sessionid` extension of the `context` MUST define a common session UUID for all the statements of a session. 


<a name="launched-attempt"></a>
## Launched Attempt

This Statement is generated from the `\mod_scormlite\event\attempt_launched` Moodle event.

- The `launchmode` extension of the `context` MUST define the content launch mode (`Normal` or `Review`). 
- The `launch-method` extension of the `context` MUST define the content launch method (`OwnWindow` or `AnyWindow`). 
- The `learner` extension of the `context` MUST be defined when the instructor reviews a learner attempt. 


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
        "id": "http://xapi.moodle.test/xapi/activities/scormlite/86e15642-5e46-45c2-8fd2-7c88d2e37edf/sco",
        "definition": {
            "type": "http://adlnet.gov/expapi/activities/lesson"
        }
    },
    "context": {
        "contextActivities": {
            "parent": [
                {
                    "id": "http://xapi.moodle.test/xapi/activities/scormlite/86e15642-5e46-45c2-8fd2-7c88d2e37edf",
                    "definition": {
                        "type": "http://vocab.xapi.fr/activities/web-content"
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
            "http://vocab.xapi.fr/extensions/platform-event": "\\mod_scormlite\\event\\attempt_launched",
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


<a name="initialized-attempt"></a>
## Initialized Attempt

This Statement is generated from the `\mod_scormlite\event\attempt_initialized` Moodle event.

- The `launchmode` extension of the `context` MUST define the content launch mode (`normal` or `review`). 
- The `launch-method` extension of the `context` MUST define the content launch method (`OwnWindow` or `AnyWindow`). 
- The `learner` extension of the `context` MUST be defined when the instructor reviews a learner attempt. 


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
        "id": "http://adlnet.gov/expapi/verbs/initialized"
    },
    "object": {
        "objectType": "Activity",
        "id": "http://xapi.moodle.test/xapi/activities/scormlite/86e15642-5e46-45c2-8fd2-7c88d2e37edf/sco",
        "definition": {
            "type": "http://adlnet.gov/expapi/activities/lesson"
        }
    },
    "context": {
        "contextActivities": {
            "parent": [
                {
                    "id": "http://xapi.moodle.test/xapi/activities/scormlite/86e15642-5e46-45c2-8fd2-7c88d2e37edf",
                    "definition": {
                        "type": "http://vocab.xapi.fr/activities/web-content"
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
            "http://vocab.xapi.fr/extensions/platform-event": "\\mod_scormlite\\event\\attempt_initialized",
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


<a name="completed-attempt"></a>
## Completed Attempt

This Statement is generated from the `\mod_scormlite\event\attempt_completed` Moodle event.

- This Statement MUST NOT be sent when the activity is completed at the same time than a `passed` or `failed` Statement.
- The `result.completion` property MUST be set to `true`.
- The `result.duration` property MUST define the time spent to complete the activity.


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
        "id": "http://adlnet.gov/expapi/verbs/completed"
    },
    "object": {
        "objectType": "Activity",
        "id": "http://xapi.moodle.test/xapi/activities/scormlite/86e15642-5e46-45c2-8fd2-7c88d2e37edf/sco",
        "definition": {
            "type": "http://adlnet.gov/expapi/activities/lesson"
        }
    },
    "result": {
        "completion": true,
        "duration": "PT50.97S"
    },
    "context": {
        "contextActivities": {
            "parent": [
                {
                    "id": "http://xapi.moodle.test/xapi/activities/scormlite/86e15642-5e46-45c2-8fd2-7c88d2e37edf",
                    "definition": {
                        "type": "http://vocab.xapi.fr/activities/web-content"
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
            "http://vocab.xapi.fr/extensions/platform-event": "\\mod_scormlite\\event\\attempt_completed",
            "http://id.tincanapi.com/extension/attempt-id": 2,
            "https://w3id.org/xapi/cmi5/context/extensions/sessionid": "7584cd21-bbea-4179-a7e9-affdea1a4444"
        }
    },
    "timestamp": "2018-06-20T16:04:17+08:00"
}
```


<a name="passed-failed-attempt"></a>
## Passed/Failed Attempt

This Statement is generated from the `\mod_scormlite\event\attempt_passed` and `\mod_scormlite\event\attempt_failed` Moodle events.

- The `result.completion` property MUST be set to `true`.
- The `result.success` property MUST be set according to the verb (`true` for a `passed` Statement, `false` for a `failed` Statement).
- The `result.score` property MUST define the score, including its `min`, `max`, `raw` and `scaled` values.
- The `result.duration` property MUST define the time spent to pass or fail the activity.
- The `masteryscore` extension of the `context` MUST define the passing score of the activity.
- The `max-time` extension of the `context` MUST define the maximum time allowed to achieve the activity (ISO 8601).


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
        "id": "http://adlnet.gov/expapi/verbs/passed"
    },
    "object": {
        "objectType": "Activity",
        "id": "http://xapi.moodle.test/xapi/activities/scormlite/86e15642-5e46-45c2-8fd2-7c88d2e37edf/sco",
        "definition": {
            "type": "http://adlnet.gov/expapi/activities/lesson"
        }
    },
    "result": {
        "completion": true,
        "success": true,
        "score": {
            "max": 100,
            "min": 0,
            "raw": 75,
            "scaled": 0.75
        },
        "duration": "PT50.97S"
    },
    "context": {
        "contextActivities": {
            "parent": [
                {
                    "id": "http://xapi.moodle.test/xapi/activities/scormlite/86e15642-5e46-45c2-8fd2-7c88d2e37edf",
                    "definition": {
                        "type": "http://vocab.xapi.fr/activities/web-content"
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
            "http://vocab.xapi.fr/extensions/platform-event": "\\mod_scormlite\\event\\attempt_passed",
            "http://id.tincanapi.com/extension/attempt-id": 2,
            "https://w3id.org/xapi/cmi5/context/extensions/sessionid": "7584cd21-bbea-4179-a7e9-affdea1a4444",
            "https://w3id.org/xapi/cmi5/context/extensions/masteryscore": 50,
            "http://vocab.xapi.fr/extensions/max-time": "PT1H"
        }
    },
    "timestamp": "2018-06-20T16:04:17+08:00"
}
```


<a name="terminated-attempt"></a>
## Terminated Attempt

This Statement is generated from the `\mod_scormlite\event\attempt_terminated` Moodle event.

- The `result.duration` property MUST define the time from the content opening and closing.
- The `launchmode` extension of the `context` MUST define the content launch mode (`normal` or `review`). 
- The `learner` extension of the `context` MUST be defined when the instructor reviews a learner attempt. 


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
        "id": "http://adlnet.gov/expapi/verbs/terminated"
    },
    "object": {
        "objectType": "Activity",
        "id": "http://xapi.moodle.test/xapi/activities/scormlite/86e15642-5e46-45c2-8fd2-7c88d2e37edf/sco",
        "definition": {
            "type": "http://adlnet.gov/expapi/activities/lesson"
        }
    },
    "result": {
        "duration": "PT0.97S"
    },
    "context": {
        "contextActivities": {
            "parent": [
                {
                    "id": "http://xapi.moodle.test/xapi/activities/scormlite/86e15642-5e46-45c2-8fd2-7c88d2e37edf",
                    "definition": {
                        "type": "http://vocab.xapi.fr/activities/web-content"
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
            "http://vocab.xapi.fr/extensions/platform-event": "\\mod_scormlite\\event\\attempt_terminated",
            "http://id.tincanapi.com/extension/attempt-id": 2,
            "https://w3id.org/xapi/cmi5/context/extensions/sessionid": "7584cd21-bbea-4179-a7e9-affdea1a4444",
            "https://w3id.org/xapi/cmi5/context/extensions/launchmode": "Review",
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



<a name="passed-failed-sco-learner"></a>
## Passed/Failed SCO (Learner)

This Statement is generated from the `\mod_scormlite\event\sco_result_updated` Moodle event, after a new attempt and when the retained score for the activity changed.

- The `result.success` property MUST be set according to the verb (`true` for a `passed` Statement, `false` for a `failed` Statement).
- The `result.score` property MUST define the relevant score, including its `min`, `max`, `raw` and `scaled` values.
- The `result.duration` property MUST define the time spent on the relevant attempt to pass or fail the activity.
- The `attempt-id` extension of the `context` MUST define the number of the kept attempt. 
- The `attempts-number` extension of the `context` MUST define the number of achieved attempts. 
- The `max-attempts` extension of the `context` MUST define the allowed number of attempts. 
- The `masteryscore` extension of the `context` MUST define the passing score of the activity.
- The `scoring-method` extension of the `context` MUST define which score is kept when there are multiple attempts (`BestAttempt`, `LastAttempt`, `FirstAttempt`).
- The `max-time` extension of the `context` MUST define the maximum time allowed to achieve the activity (ISO 8601).


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
        "id": "http://xapi.moodle.test/xapi/activities/scormlite/86e15642-5e46-45c2-8fd2-7c88d2e37edf",
        "definition": {
            "type": "http://vocab.xapi.fr/activities/web-content",
            "name": {
                "en": "SCORM Lite activity"
            },
            "description": {
                "en": "SCORM Lite activity description"
            },
            "extensions": {
                "http://vocab.xapi.fr/extensions/platform-concept": "scormlite",
                "http://vocab.xapi.fr/extensions/concept-family": "resource",
                "http://vocab.xapi.fr/extensions/standard": "scorm"
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
                    "id": "http://xapi.moodle.test/xapi/activities/course/54b9d6f3-c14b-4abf-b613-f5e5fb5ecd40",
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
            ],
        },
        "platform": "Moodle",
        "extensions": {
            "http://vocab.xapi.fr/extensions/platform-event": "\\mod_scormlite\\event\\sco_result_updated",
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


<a name="passed-failed-sco-instructor"></a>
## Passed/Failed SCO (Instructor)

This Statement is generated from the `\mod_scormlite\event\sco_result_changed` Moodle event, when an instructor manually changes the score of a learner.
It differs from the previous one on the following rules: 

- The `result.duration` property MUST NOT be set.
- The `context.instructor` property MUST be set.
- The `attempt-id` extension of the `context` MUST NOT be set.
- The `attempts-number` extension of the `context` MUST NOT be set. 
- The `max-attempts` extension of the `context` MUST NOT be set. 
- The `scoring-method` extension of the `context` MUST NOT be set.
- The `max-time` extension of the `context` MUST NOT be set.


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
        "id": "http://xapi.moodle.test/xapi/activities/scormlite/86e15642-5e46-45c2-8fd2-7c88d2e37edf",
        "definition": {
            "type": "http://vocab.xapi.fr/activities/web-content",
            "name": {
                "en": "SCORM Lite activity"
            },
            "description": {
                "en": "SCORM Lite activity description"
            },
            "extensions": {
                "http://vocab.xapi.fr/extensions/platform-concept": "scormlite",
                "http://vocab.xapi.fr/extensions/concept-family": "resource",
                "http://vocab.xapi.fr/extensions/standard": "scorm"
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
        }
    },
    "context": {
        "contextActivities": {
            "parent": [
                {
                    "id": "http://xapi.moodle.test/xapi/activities/course/54b9d6f3-c14b-4abf-b613-f5e5fb5ecd40",
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
            ],
        },
        "instructor": {
            "objectType": "Agent",
            "account": {
                "name": "d0d6cd21-bbea-4179-a7e9-affdea1a1d84",
                "homePage": "http://xapi.moodle.test"
            }
        },
        "platform": "Moodle",
        "extensions": {
            "http://vocab.xapi.fr/extensions/platform-event": "\\mod_scormlite\\event\\sco_result_changed",
            "https://w3id.org/xapi/cmi5/context/extensions/masteryscore": 50
        }
    },
    "timestamp": "2018-06-20T16:04:17+08:00"
}
```


<a name="nav-in-module"></a>
## Navigated-In Module

This Statement is generated from the `\mod_scormlite\event\course_module_viewed` event 
and follows the same rules than other modules (see [navigation events](events_nav#nav-in-module)).



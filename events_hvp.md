# Moodle / VLE Profile: H5P Statements

---

- [Supported Statements](#statements)
- [Common rules](#common-rules)
- [Question Answered](#question-answered)
- [Summary Answered](#summary-answered)
- [Quiz Completed](#quiz-completed)
- [Course Presentation Completed](#pres-completed)
- [Navigated-In Course Presentation](#nav-in-pres)


<a name="statements"></a>
## Supported Statements

### H5P Statements
- Question Answered
- Summary Answered
- Quiz Completed
- Course Presentation Completed
- Navigated-In Course Presentation

### Course Module Statements
- Navigated-In Course Module (on Moodle viewed event)
- Completed Course Module (on Moodle completion event)
- Graded Course Module (on Moodle grading event)


<a name="common-rules"></a>
## Common rules

The following rules apply for all the H5P generated statements:

- The `actor` MUST be replaced by the authenticated user, as defined by the VLE profile.
- The `verb.id` MUST be adapted depending of the `result` properties (`passed`, `failed`, `scored`, `completed`).
- The `verb.display` property MAY be removed.
- The `object` and the `context` MUST be adapted to conform with the Moodle / VLE Profile.
- The `object.extensions` which are H5P-specific MAY be removed.
- The `context.contextActivities.parent` of H5P nested activities MUST be the direct parent of the `object` as it is defined in the H5P statement.
- All other elements of the statements MUST be kept without modification.


<a name="question-answered"></a>
## Question Answered

This statement is generated from the `\logstore_trax\event\hvp_question_answered` event.
Its granularity level MUST be `inside-learning-unit` and its object type is always `cmi.interaction`.


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
        "id": "http://adlnet.gov/expapi/verbs/answered"
    },
    "object": {
        "objectType": "Activity",
        "id": "http://xapi.moodle.test/xapi/activities/hvp/86e15642-5e46-45c2-8fd2-7c88d2e37edf/question/2a8984c5-0dd8-4fe5-affc-585cf792d06f",
        "definition": {
            "type": "http://adlnet.gov/expapi/activities/cmi.interaction",
            "name": {
                "fr": "Here is the title of the question..."
            },
            "description": {
                "fr": "Here is the description of the question..."
            },
            "interactionType": "true-false",
            "correctResponsesPattern": [
                "true"
            ]
        }
    },
    "result": {
        "score": {
            "max": 1,
            "min": 0,
            "raw": 0,
            "scaled": 0
        },
        "success": false,
        "duration": "PT0.97S",
        "response": "false",
        "completion": true
    },
    "context": {
        "contextActivities": {
            "parent": [
                {
                    "objectType": "Activity",
                    "id": "http://xapi.moodle.test/xapi/activities/hvp/86e15642-5e46-45c2-8fd2-7c88d2e37edf",
                    "definition": {
                        "type": "http://vocab.xapi.fr/activities/quiz"
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
                },
                {
                    "objectType": "Activity",
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
                }
            ],
        },
        "platform": "Moodle",
        "extensions": {
            "http://vocab.xapi.fr/extensions/platform-event": "\\logstore_trax\\event\\hvp_question_answered"
        }
    },
    "timestamp": "2018-06-20T16:04:17+08:00"
}
```


<a name="summary-answered"></a>
## Summary Answered

This Statement is generated from the `\logstore_trax\event\hvp_summary_answered` event.
Its granularity level may be `learning-unit` (when the H5P activity itself is a Summary) 
or `inside-learning-unit` (when the Summary is embedded inside the H5P activity).


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
        "id": "http://xapi.moodle.test/xapi/activities/hvp/86e15642-5e46-45c2-8fd2-7c88d2e37edf",
        "definition": {
            "type": "http://vocab.xapi.fr/activities/quiz",
            "name": {
                "fr": "Here is the title of the activity..."
            },
            "description": {
                "fr": "Here is the description of the activity..."
            },
            "extensions": {
                "http://vocab.xapi.fr/extensions/concept-family": "assessment",
                "http://vocab.xapi.fr/extensions/platform-concept": "hvp-summary"
            }
        }
    },
    "result": {
        "score": {
            "max": 5,
            "min": 0,
            "raw": 2,
            "scaled": 0.4
        },
        "duration": "PT64.03S",
        "completion": true
    },
    "context": {
        "contextActivities": {
            "parent": [
                {
                    "objectType": "Activity",
                    "id": "http://xapi.moodle.test/xapi/activities/course/54b9d6f3-c14b-4abf-b613-f5e5fb5ecd40",
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
            ],
        },
        "platform": "Moodle",
        "extensions": {
            "http://vocab.xapi.fr/extensions/platform-event": "\\logstore_trax\\event\\hvp_summary_answered"
        }
    },
    "timestamp": "2018-06-20T16:04:17+08:00"
}
```


<a name="quiz-completed"></a>
## Quiz Completed

This Statement is generated from the `\logstore_trax\event\hvp_quiz_completed` event.
Its granularity level may be `learning-unit` (when the H5P activity itself is a Quiz) 
or `inside-learning-unit` (when the Quiz is embedded inside the H5P activity).


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
        "id": "http://xapi.moodle.test/xapi/activities/hvp/86e15642-5e46-45c2-8fd2-7c88d2e37edf",
        "definition": {
            "type": "http://vocab.xapi.fr/activities/quiz",
            "name": {
                "fr": "Here is the title of the activity..."
            },
            "description": {
                "fr": "Here is the description of the activity..."
            },
            "extensions": {
                "http://vocab.xapi.fr/extensions/concept-family": "assessment",
                "http://vocab.xapi.fr/extensions/platform-concept": "hvp-quiz"
            }
        }
    },
    "result": {
        "score": {
            "max": 5,
            "min": 0,
            "raw": 2,
            "scaled": 0.4
        },
        "success": false,
        "duration": "PT64.03S",
        "completion": true
    },
    "context": {
        "contextActivities": {
            "parent": [
                {
                    "objectType": "Activity",
                    "id": "http://xapi.moodle.test/xapi/activities/course/54b9d6f3-c14b-4abf-b613-f5e5fb5ecd40",
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
            ],
        },
        "platform": "Moodle",
        "extensions": {
            "http://vocab.xapi.fr/extensions/platform-event": "\\logstore_trax\\event\\hvp_quiz_completed"
        }
    },
    "timestamp": "2018-06-20T16:04:17+08:00"
}
```


<a name="pres-completed"></a>
## Course Presentation Completed

This Statement is generated from the `\logstore_trax\event\hvp_course_presentation_completed` event.
Its granularity level may be `learning-unit` (when the H5P activity itself is a Quiz) 
or `inside-learning-unit` (when the Quiz is embedded inside the H5P activity).


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
        "id": "http://xapi.moodle.test/xapi/activities/hvp/86e15642-5e46-45c2-8fd2-7c88d2e37edf",
        "definition": {
            "type": "http://vocab.xapi.fr/activities/web-content",
            "name": {
                "fr": "Here is the title of the activity..."
            },
            "description": {
                "fr": "Here is the description of the activity..."
            },
            "extensions": {
                "http://vocab.xapi.fr/extensions/concept-family": "resource",
                "http://vocab.xapi.fr/extensions/platform-concept": "hvp-course-presentation"
            }
        }
    },
    "result": {
        "score": {
            "max": 5,
            "min": 0,
            "raw": 2,
            "scaled": 0.4
        },
        "duration": "PT64.03S",
        "completion": true
    },
    "context": {
        "contextActivities": {
            "parent": [
                {
                    "objectType": "Activity",
                    "id": "http://xapi.moodle.test/xapi/activities/course/54b9d6f3-c14b-4abf-b613-f5e5fb5ecd40",
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
            ],
        },
        "platform": "Moodle",
        "extensions": {
            "http://vocab.xapi.fr/extensions/platform-event": "\\logstore_trax\\event\\hvp_course_presentation_completed"
        }
    },
    "timestamp": "2018-06-20T16:04:17+08:00"
}
```


<a name="nav-in-pres"></a>
## Navigated-In Course Presentation

This Statement is generated from the `\logstore_trax\event\hvp_course_presentation_progressed` event.
Its granularity level may be `learning-unit` (when the H5P activity itself is a Quiz) 
or `inside-learning-unit` (when the Quiz is embedded inside the H5P activity).


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
        "id": "http://vocab.xapi.fr/verbs/navigated-in"
    },
    "object": {
        "objectType": "Activity",
        "id": "http://xapi.moodle.test/xapi/activities/hvp/86e15642-5e46-45c2-8fd2-7c88d2e37edf",
        "definition": {
            "type": "http://vocab.xapi.fr/activities/web-content",
            "name": {
                "fr": "Here is the title of the activity..."
            },
            "description": {
                "fr": "Here is the description of the activity..."
            },
            "extensions": {
                "http://vocab.xapi.fr/extensions/concept-family": "resource",
                "http://vocab.xapi.fr/extensions/platform-concept": "hvp-course-presentation"
            }
        }
    },
    "context": {
        "contextActivities": {
            "parent": [
                {
                    "objectType": "Activity",
                    "id": "http://xapi.moodle.test/xapi/activities/course/54b9d6f3-c14b-4abf-b613-f5e5fb5ecd40",
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
            ],
        },
        "platform": "Moodle",
        "extensions": {
            "http://vocab.xapi.fr/extensions/platform-event": "\\logstore_trax\\event\\hvp_course_presentation_progressed"
        }
    },
    "timestamp": "2018-06-20T16:04:17+08:00"
}
```



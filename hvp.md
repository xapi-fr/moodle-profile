# Moodle Profile: H5P events

---

- [Common rules](#common-rules)
- [Completed Quiz](#completed-quiz)
- [Answered Quiz Question](#answered-quiz-question)
- [Answered Single Question](#answered-single-question)
- [Course Module Viewed](#course-module-viewed)


<a name="common-rules"></a>
## Common rules

- All VLE and Moodle profile rules apply.
- The H5P `actor` MUST be replaced by the actor as it is defined for all the other platform Statements.
- The H5P `verb` MAY be kept without the `display` property.
- The H5P `object` MUST be modified depending of its type (see below).
- The H5P `result` MUST be kept without modification.
- The H5P `context` MUST be replaced by the context as it is defined for all the other platform Statements.


<a name="completed-quiz"></a>
## Completed Quiz

This Statement is generated from the H5P Statement (javascript).

- The activity `type` MUST be `http://vocab.xapi.fr/activities/quiz`.
- The activity `platform-concept` extension MUST be `hvp-quiz`.
- The activity `concept-family` extension MUST be `assessment`.
- The contextual `granularity-level` activity MUST be `http://vocab.xapi.fr/categories/learning-unit`.


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
        "platform": "Moodle"
    },
    "timestamp": "2018-06-20T16:04:17+08:00"
}
```


<a name="answered-quiz-question"></a>
## Answered Quiz Question

This Statement is generated from the H5P Statement (javascript).

- The `object` MUST be the same as the H5P Statement object, except its `id`, `name`, `description` and `extensions`.
- The `object.id` MUST be an extension of the contextual `parent` activity IRI.
- The lang string keys of the object `name` and `description` (e.g. `en-US`) MUST be set accordingly to the course or platform settings.
- The object `description` MAY be moved to the `name` when the `name` is not defined and the `description` is defined.
- The `object.definition.extensions` of the H5P Statement MAY be removed.
- The contextual `parent` activity MUST be the Moodle H5P activity as it is defined in the [Course Module Viewed](#course-module-viewed) event.
- The contextual `granularity-level` activity MUST be `http://vocab.xapi.fr/categories/inside-learning-unit`.


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
        "platform": "Moodle"
    },
    "timestamp": "2018-06-20T16:04:17+08:00"
}
```


<a name="answered-single-question"></a>
## Answered Single Question

This Statement is generated from the H5P Statement (javascript).

- The `object` MUST be the same as the H5P Statement object, except its `id`, `name`, `description` and `extensions`.
- The `object.id` MUST be an extension of the contextual `parent` activity IRI.
- The lang string keys of the object `name` and `description` (e.g. `en-US`) MUST be set accordingly to the course or platform settings.
- The `object.definition.extensions` of the H5P Statement MAY be removed.
- The contextual `parent` activity MUST be the Moodle H5P activity as it is defined in the [Course Module Viewed](#course-module-viewed) event.
- The contextual `granularity-level` activity MUST be `http://vocab.xapi.fr/categories/inside-learning-unit`.


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
        "id": "http://xapi.moodle.test/xapi/activities/hvp/50b4c4f6-4623-42af-8cb8-6f9d0a1d9efc/question",
        "definition": {
            "type": "http://adlnet.gov/expapi/activities/cmi.interaction",
            "name": {
                "fr": "Here is the title of the activity..."
            },
            "description": {
                "fr": "Here is the question itself..."
            },
            "interactionType": "choice",
            "choices": [
                {
                    "id": "0",
                    "description": {
                        "en-US": "Response 1"
                    }
                },
                {
                    "id": "1",
                    "description": {
                        "en-US": "Response 2"
                    }
                }
            ],
            "correctResponsesPattern": [
                "0"
            ]
        }
    },
    "result": {
        "score": {
            "max": 1,
            "min": 0,
            "raw": 1,
            "scaled": 1
        },
        "success": true,
        "duration": "PT56.15S",
        "response": "0",
        "completion": true
    },
    "context": {
        "contextActivities": {
            "parent": [
                {
                    "objectType": "Activity",
                    "id": "http://xapi.moodle.test/xapi/activities/hvp/50b4c4f6-4623-42af-8cb8-6f9d0a1d9efc",
                    "definition": {
                        "type": "http://vocab.xapi.fr/activities/poll"
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
            ]
        },
        "platform": "Moodle"
    },
    "timestamp": "2018-06-20T16:04:17+08:00"
}
```



<a name="course-module-viewed"></a>
## Course Module Viewed

This Statement is generated from the `\mod_hvp\event\course_module_viewed`.

- The activity `type` MUST be `http://vocab.xapi.fr/activities/poll` (single question) or `http://vocab.xapi.fr/activities/quiz` (quiz / questions set).
- The activity `platform-concept` extension MUST be `hvp-poll` (single question) or `hvp-quiz` (quiz / questions set).
- The activity `concept-family` extension MUST be `feedback` (single question) or `assessment` (quiz / questions set).
- The contextual `granularity-level` activity MUST be `http://vocab.xapi.fr/categories/learning-unit`.


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
        "id": "http://xapi.moodle.test/xapi/activities/hvp/50b4c4f6-4623-42af-8cb8-6f9d0a1d9efc",
        "definition": {
            "type": "http://vocab.xapi.fr/activities/poll",
            "name": {
                "fr": "Here is the title of the activity..."
            },
            "description": {
                "fr": "Here is the description of the activity..."
            },
            "extensions": {
                "http://vocab.xapi.fr/extensions/concept-family": "feedback",
                "http://vocab.xapi.fr/extensions/platform-concept": "hvp-poll"
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
        "platform": "Moodle"
    },
    "timestamp": "2018-06-20T16:04:17+08:00"
}
```


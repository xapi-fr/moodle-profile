# Moodle / VLE Profile: TrainingPath Statements

---

- [Supported Statements](#statements)
- [Identification Schema](#id)
- [Activity Types](#types)
- [Common Rules](#common-rules)
- [Navigated-In Course Module](#nav-in-module)
- [Navigated-In Item](#nav-in-item)
- [Completed Item](#completed-item)
- [Passed / Failed Assessment](#passed-failed-item)


<a name="statements"></a>
## Supported Statements

### SCORM Lite Statements
- Launched Attempt
- Initialized Attempt
- Completed Attempt
- Passed / Failed Attempt
- Terminated Attempt

### Training Path Statements
- Navigated-In Item (all levels and types)
- Completed Item (all levels and types, except Assessment)
- Passed / Failed Assessment


<a name="id"></a>
## Identification Schema

- TrainingPath Course Module: `<platform-iri>/xapi/activities/trainingpath/<uuid>`
- TrainingPath Theme: `<platform-iri>/xapi/activities/trainingpath/<uuid>/theme/<uuid>`
- TrainingPath Phase: `<platform-iri>/xapi/activities/trainingpath/<uuid>/phase/<uuid>`
- TrainingPath Sequence: `<platform-iri>/xapi/activities/trainingpath/<uuid>/sequence/<uuid>`
- TrainingPath Activity: `<platform-iri>/xapi/activities/trainingpath/<uuid>/activity/<uuid>`
- TrainingPath SCO: `<platform-iri>/xapi/activities/trainingpath/<uuid>/activity/<uuid>/sco`


<a name="types"></a>
## Activity Types

- TrainingPath Course Module: `http://vocab.xapi.fr/activities/training-program`
- TrainingPath Theme: `http://vocab.xapi.fr/activities/training-module`
- TrainingPath Phase: `http://vocab.xapi.fr/activities/training-phase`
- TrainingPath Sequence: `http://vocab.xapi.fr/activities/training-sequence`

- TrainingPath Content: `http://vocab.xapi.fr/activities/web-content`
- TrainingPath Assessment: `http://vocab.xapi.fr/activities/quiz`
- TrainingPath Onsite Classroom: `http://vocab.xapi.fr/activities/face-to-face`
- TrainingPath Virtual Classroom: `http://vocab.xapi.fr/activities/live-session`
- TrainingPath File: `http://adlnet.gov/expapi/activities/file`
- TrainingPath Rich Text: `http://vocab.xapi.fr/activities/web-page`

- TrainingPath SCO: `http://vocab.xapi.fr/activities/content-object`


<a name="common-rules"></a>
## Common Rules


## Attempt Statements

SCORM Lite rules apply, except the following:

- The `object.id` property MUST define the content object (SCO) ID following the TrainingPath identification schema.
- The `context.contextActivities.parent` property MUST include the TrainingPath activity.
- The `context.contextActivities.grouping` property MUST include the TrainingPath sequence.
- The `context.contextActivities.grouping` property MUST include the TrainingPath phase.
- The `context.contextActivities.grouping` property MUST include the TrainingPath theme.
- The `context.contextActivities.grouping` property MUST include the TrainingPath course module.


## Activity Statements

- The `object` property MUST define the TrainingPath activity with the matching `type`.
- The `object.definition.name` property MUST define the activity code.
- The `object.definition.description` property MUST define the activity title.
- The `position` extension of the `object` MUST define the position of the activity in its sequence.
- The `duration` extension of the `object` MUST define the minimum study time for the content activity or the scheduled duration of the classroom session.
- The `mandatory` extension of the `object` MUST be set to `true` for mandatory activities et `false` for optionnal activities.
- The `remedial` extension of the `object` MUST be set to `true` or `false` for all the assessment activities.
- The `context.contextActivities.parent` property MUST include the TrainingPath sequence.
- The `context.contextActivities.grouping` property MUST include the TrainingPath phase.
- The `context.contextActivities.grouping` property MUST include the TrainingPath theme.
- The `context.contextActivities.grouping` property MUST include the TrainingPath course module.
- The `context.contextActivities.category` property MUST include a granularity level set to `inside-learning-unit`.


## Sequence Statements

- The `object` property MUST define the TrainingPath sequence.
- The `object.definition.name` property MUST define the sequence code.
- The `object.definition.description` property MUST define the sequence title.
- The `position` extension of the `object` MUST define the position of the sequence in its phase.
- The `context.contextActivities.parent` property MUST include the TrainingPath phase.
- The `context.contextActivities.grouping` property MUST include the TrainingPath theme.
- The `context.contextActivities.grouping` property MUST include the TrainingPath course module.
- The `context.contextActivities.category` property MUST include a granularity level set to `inside-learning-unit`.


## Phase Statements

- The `object` property MUST define the TrainingPath phase.
- The `object.definition.name` property MUST define the phase code.
- The `object.definition.description` property MUST define the phase title.
- The `position` extension of the `object` MUST define the position of the phase in the course module.
- The `context.contextActivities.parent` property MUST include the TrainingPath course module.
- The `context.contextActivities.category` property MUST include a granularity level set to `inside-learning-unit`.


## Theme Statements

- The `object` property MUST define the TrainingPath theme.
- The `object.definition.name` property MUST define the theme code.
- The `object.definition.description` property MUST define the theme title.
- The `position` extension of the `object` MUST define the position of the theme in the course module.
- The `duration` extension of the `object` MUST define the minimum study time for the theme.
- The `context.contextActivities.parent` property MUST include the TrainingPath course module.
- The `context.contextActivities.category` property MUST include a granularity level set to `inside-learning-unit`.


<a name="nav-in-module"></a>
## Navigated-In Course Module

This Statement is generated from the `\core\event\course_module_viewed` event (main page) or from the `\mod_trainingpath\event\page_viewed` event (secondary pages).

- The `page` extension of the `context` MUST be set to `themes`, `phases` or `gradebook` when the user opens the related pages.
- The `page` extension of the `context` MUST NOT be set when the user opens the main page.


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
        "id": "http://xapi.moodle.test/xapi/activities/trainingpath/86e15642-5e46-45c2-8fd2-7c88d2e37edf",
        "definition": {
            "type": "http://vocab.xapi.fr/activities/training-program",
            "name": {
                "en": "Training Path code"
            },
            "description": {
                "en": "Training Path title"
            },
            "extensions": {
                "http://vocab.xapi.fr/extensions/platform-concept": "trainingpath"
            }
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
                    "id": "http://vocab.xapi.fr/categories/moodle/trainingpath",
                    "definition": {
                        "type": "http://adlnet.gov/expapi/activities/profile"
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
            "http://vocab.xapi.fr/extensions/platform-event": "\\mod_trainingpath\\event\\page_viewed",
            "http://vocab.xapi.fr/extensions/page": "phases"
        }
    },
    "timestamp": "2018-06-20T16:04:17+08:00"
}
```


<a name="nav-in-item"></a>
## Navigated-In Item

This Statement is generated from the `\mod_trainingpath\event\item_viewed` event.

- The `object` and `context` properties MUST be defined depending of the type of item.


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
        "id": "http://xapi.moodle.test/xapi/activities/trainingpath/86e15642-5e46-45c2-8fd2-7c88d2e37edf/phase/d0d6cd21-5e46-45c2-8fd2-affdea1a1d84",
        "definition": {
            "type": "http://vocab.xapi.fr/activities/training-phase",
            "name": {
                "en": "Training Path phase code"
            },
            "description": {
                "en": "Training Path phase title"
            },
            "extensions": {
                "http://id.tincanapi.com/extension/position": 2
            }
        }
    },
    "context": {
        "contextActivities": {
            "parent": [
                {
                    "objectType": "Activity",
                    "id": "http://xapi.moodle.test/xapi/activities/trainingpath/86e15642-5e46-45c2-8fd2-7c88d2e37edf",
                    "definition": {
                        "type": "http://vocab.xapi.fr/activities/training-program"
                    }
                }
            ],
            "grouping": [
                {
                    "objectType": "Activity",
                    "id": "http://xapi.moodle.test/xapi/activities/course/ba297687-b1aa-4477-9efd-a782c8fdb90a",
                    "definition": {
                        "type": "http://vocab.xapi.fr/activities/course"
                    }
                },
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
                    "id": "http://vocab.xapi.fr/categories/inside-learning-unit",
                    "definition": {
                        "type": "http://vocab.xapi.fr/activities/granularity-level"
                    }
                },
                {
                    "id": "http://vocab.xapi.fr/categories/moodle/trainingpath",
                    "definition": {
                        "type": "http://adlnet.gov/expapi/activities/profile"
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
            "http://vocab.xapi.fr/extensions/platform-event": "\\mod_trainingpath\\event\\item_viewed"
        }
    },
    "timestamp": "2018-06-20T16:04:17+08:00"
}
```


<a name="completed-item"></a>
## Completed Item

This Statement is generated from the `\mod_trainingpath\event\item_completed` event (completion by learner) or from the `\mod_trainingpath\event\item_completion_forced` event (completion forced by instructor).

- The `object` and `context` properties MUST be defined depending of the type of item.
- The `result.completion` property MUST be set to `true`.
- The `result.duration` property MUST define the time spent by the user.
- The `result.success` property MUST be set when it is known.
- The `result.score` property MUST be set when it is known, including the `min`, `max`, `raw` and `scaled` values.
- The `remedial-success` extension of the `result` property MUST be set when it is known.
- The `remedial-score` extension of the `result` property MUST be set when it is known.
- The `context.instructor` property MUST be define the instructor who forced the completion (content) or filled-in the attending form (classroom session).


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
        "id": "http://xapi.moodle.test/xapi/activities/trainingpath/86e15642-5e46-45c2-8fd2-7c88d2e37edf/phase/d0d6cd21-5e46-45c2-8fd2-affdea1a1d84",
        "definition": {
            "type": "http://vocab.xapi.fr/activities/training-phase",
            "name": {
                "en": "Training Path phase code"
            },
            "description": {
                "en": "Training Path phase title"
            },
            "extensions": {
                "http://id.tincanapi.com/extension/position": 2
            }
        }
    },
    "result": {
        "completion": true,
        "duration": "PT50.97S",
        "success": false,
        "score": {
            "max": 100,
            "min": 0,
            "raw": 25,
            "scaled": 0.25
        },
        "extensions": {
            "http://vocab.xapi.fr/extensions/remedial-success": true,
            "http://vocab.xapi.fr/extensions/remedial-score": {
                "max": 100,
                "min": 0,
                "raw": 75,
                "scaled": 0.75
            }
        }
    },
    "context": {
        "contextActivities": {
            "parent": [
                {
                    "objectType": "Activity",
                    "id": "http://xapi.moodle.test/xapi/activities/trainingpath/86e15642-5e46-45c2-8fd2-7c88d2e37edf",
                    "definition": {
                        "type": "http://vocab.xapi.fr/activities/training-program"
                    }
                }
            ],
            "grouping": [
                {
                    "objectType": "Activity",
                    "id": "http://xapi.moodle.test/xapi/activities/course/ba297687-b1aa-4477-9efd-a782c8fdb90a",
                    "definition": {
                        "type": "http://vocab.xapi.fr/activities/course"
                    }
                },
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
                    "id": "http://vocab.xapi.fr/categories/inside-learning-unit",
                    "definition": {
                        "type": "http://vocab.xapi.fr/activities/granularity-level"
                    }
                },
                {
                    "id": "http://vocab.xapi.fr/categories/moodle/trainingpath",
                    "definition": {
                        "type": "http://adlnet.gov/expapi/activities/profile"
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
            "http://vocab.xapi.fr/extensions/platform-event": "\\mod_trainingpath\\event\\item_completed"
        }
    },
    "timestamp": "2018-06-20T16:04:17+08:00"
}
```


<a name="passed-failed-item"></a>
## Passed / Failed Assessment

This Statement is generated from the `\mod_trainingpath\event\item_result_updated` event (score obtained by learner) or from the `\mod_trainingpath\event\item_result_forced` event (score forced by instructor).

- The `result.success` property MUST be set.
- The `result.score` property MUST be set, including the `min`, `max`, `raw` and `scaled` values.
- The `result.completion` property MUST be set to `true`.
- The `context.instructor` property MUST be define the instructor who forced the score of the assessment.


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
        "id": "http://xapi.moodle.test/xapi/activities/trainingpath/86e15642-5e46-45c2-8fd2-7c88d2e37edf/activity/d0d6cd21-5e46-45c2-8fd2-affdea1a1d84",
        "definition": {
            "type": "http://vocab.xapi.fr/activities/quiz",
            "name": {
                "en": "Training Path assessment code"
            },
            "description": {
                "en": "Training Path assessment title"
            },
            "extensions": {
                "http://id.tincanapi.com/extension/position": 2,
                "http://vocab.xapi.fr/extensions/mandatory": true,
                "http://vocab.xapi.fr/extensions/remedial": false
            }
        }
    },
    "result": {
        "completion": true,
        "success": false,
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
                    "id": "http://xapi.moodle.test/xapi/activities/trainingpath/86e15642-5e46-45c2-8fd2-7c88d2e37edf/sequence/d0d6cd21-5e46-45c2-8fd2-affdea1a1d84",
                    "definition": {
                        "type": "http://vocab.xapi.fr/activities/training-sequence"
                    }
                },
            ],
            "grouping": [
                {
                    "objectType": "Activity",
                    "id": "http://xapi.moodle.test/xapi/activities/trainingpath/86e15642-5e46-45c2-8fd2-7c88d2e37edf/phase/d0d6cd21-5e46-45c2-8fd2-affdea1a1d84",
                    "definition": {
                        "type": "http://vocab.xapi.fr/activities/training-phase"
                    }
                },
                {
                    "objectType": "Activity",
                    "id": "http://xapi.moodle.test/xapi/activities/trainingpath/86e15642-5e46-45c2-8fd2-7c88d2e37edf/theme/d0d6cd21-5e46-45c2-8fd2-affdea1a1d84",
                    "definition": {
                        "type": "http://vocab.xapi.fr/activities/training-module"
                    }
                },
                {
                    "objectType": "Activity",
                    "id": "http://xapi.moodle.test/xapi/activities/trainingpath/86e15642-5e46-45c2-8fd2-7c88d2e37edf",
                    "definition": {
                        "type": "http://vocab.xapi.fr/activities/training-program"
                    }
                },
                {
                    "objectType": "Activity",
                    "id": "http://xapi.moodle.test/xapi/activities/course/ba297687-b1aa-4477-9efd-a782c8fdb90a",
                    "definition": {
                        "type": "http://vocab.xapi.fr/activities/course"
                    }
                },
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
                    "id": "http://vocab.xapi.fr/categories/inside-learning-unit",
                    "definition": {
                        "type": "http://vocab.xapi.fr/activities/granularity-level"
                    }
                },
                {
                    "id": "http://vocab.xapi.fr/categories/moodle/trainingpath",
                    "definition": {
                        "type": "http://adlnet.gov/expapi/activities/profile"
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
        "instructor": {
            "objectType": "Agent",
            "account": {
                "name": "d0d6cd21-bbea-4179-a7e9-affdea1a1d84",
                "homePage": "http://xapi.moodle.test"
            }
        },
        "platform": "Moodle",
        "extensions": {
            "http://vocab.xapi.fr/extensions/platform-event": "\\mod_trainingpath\\event\\item_result_forced"
        }
    },
    "timestamp": "2018-06-20T16:04:17+08:00"
}
```



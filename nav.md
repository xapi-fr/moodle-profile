# Moodle Profile: Navigation events

---

- [Logged-In](#logged-in)
- [Logged-Out](#logged-out)
- [Navigated-In Course](#nav-in-course)
- [Navigated-In Module](#nav-in-module)


<a name="logged-in"></a>
## Logged-In

This Statement is generated from the `\core\event\user_loggedin` Moodle event.

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
        "id": "https://w3id.org/xapi/adl/verbs/logged-in"
    },
    "object": {
        "objectType": "Activity",
        "id": "http://xapi.moodle.test",
        "definition": {
            "type": "http://vocab.xapi.fr/activities/system",
            "name": {
                "en": "Moodle test site"
            }
        }
    },
    "context": {
        "contextActivities": {
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


<a name="logged-out"></a>
## Logged-Out

This Statement is generated from the `\core\event\user_loggedout` Moodle event.

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
        "id": "https://w3id.org/xapi/adl/verbs/logged-out"
    },
    "object": {
        "objectType": "Activity",
        "id": "http://xapi.moodle.test",
        "definition": {
            "type": "http://vocab.xapi.fr/activities/system",
            "name": {
                "en": "Moodle test site"
            }
        }
    },
    "context": {
        "contextActivities": {
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


<a name="nav-in-course"></a>
## Navigated-In Course

This Statement is generated from the `\core\event\course_viewed` Moodle event.

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

<a name="nav-in-course-category"></a>
## Navigated-In Course Category

This Statement is generated from the `\core\event\course_category_viewed` Moodle event.

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
        "id": "http://xapi.moodle.test/xapi/activities/course_category/ba297687-b1aa-4477-9efd-a782c8fdb90a",
        "definition": {
            "type": "http://vocab.xapi.fr/activities/course_category",
            "name": {
                "en": "Course category 1"
            },
            "description": {
                "en": "Course category 1 description"
            },
            "extensions": {
                "http://vocab.xapi.fr/extensions/platform-concept": "course_category"
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

<a name="nav-in-module"></a>
## Navigated-In Module

This Statement is generated from the `\xxx\event\course_module_viewed` Moodle event, where `xxx` is the name of a Moodle module (e.g. `mod_book`, `mod_chat`, `mod_choice`, etc.).

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

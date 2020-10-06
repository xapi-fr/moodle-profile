# Moodle / VLE Profile: SCORM Statements

---

- [Supported Statements](#statements)
- [Viewed Discussion](#viewed-discussion)
- [Created Discussion](#created-discussion)
- [Created Post](#created-post)


<a name="statements"></a>
## Supported Statements

### Forum Statements
- Viewed Discussion
- Created Discussion
- Created Post

### Course Module Statements
- Navigated-In Course Module (on Moodle viewed event)
- Completed Course Module (on Moodle completion event)


<a name="viewed-discussion"></a>
## Viewed Discussion

This Statement is generated from the `\mod_forum\event\discussion_viewed` Moodle event.

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
        "id": "http://id.tincanapi.com/verb/viewed"
    },
    "object": {
        "objectType": "Activity",
        "id": "http://xapi.moodle.com/xapi/activities/forum/b3192e37-6d57-4a6b-8642-b9259276440d/discussion/123",
        "definition": {
            "type": "http://id.tincanapi.com/activitytype/forum-topic",
            "name": {
                "en": "Forum discussion"
            }
        }
    },
    "context": {
        "contextActivities": {
            "parent": [
                {
                    "id": "http://xapi.moodle.com/xapi/activities/forum/21c872e3-e5fc-42ee-8f34-cc45a91ed777",
                    "definition": {
                        "type": "http://vocab.xapi.fr/activities/forum"
                    }
                }
            ],
            "grouping": [
                {
                    "id": "http://xapi.moodle.com",
                    "definition": {
                        "type": "http://vocab.xapi.fr/activities/system"
                    }
                },
                {
                    "id": "http://xapi.moodle.com/xapi/activities/course/5305a8f7-943f-4647-bc69-74ccd52e9921",
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
                    "id": "http://vocab.xapi.fr/categories/moodle/forum",
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
            "http://vocab.xapi.fr/extensions/platform-event": "\\mod_forum\\event\\discussion_viewed"
        }
    },
    "timestamp": "2019-08-14T17:20:52+02:00"
}
```


<a name="created-discussion"></a>
## Created Discussion

This Statement is generated from the `\mod_forum\event\discussion_created` Moodle event.

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
        "id": "https://w3id.org/xapi/dod-isd/verbs/created"
    },
    "object": {
        "objectType": "Activity",
        "id": "http://xapi.moodle.com/xapi/activities/forum/b3192e37-6d57-4a6b-8642-b9259276440d/discussion/123",
        "definition": {
            "type": "http://id.tincanapi.com/activitytype/forum-topic",
            "name": {
                "en": "Forum discussion"
            },
            "description": {
                "en": "Message to introduce the discussion..."
            }
        }
    },
    "context": {
        "contextActivities": {
            "parent": [
                {
                    "id": "http://xapi.moodle.com/xapi/activities/forum/21c872e3-e5fc-42ee-8f34-cc45a91ed777",
                    "definition": {
                        "type": "http://vocab.xapi.fr/activities/forum"
                    }
                }
            ],
            "grouping": [
                {
                    "id": "http://xapi.moodle.com",
                    "definition": {
                        "type": "http://vocab.xapi.fr/activities/system"
                    }
                },
                {
                    "id": "http://xapi.moodle.com/xapi/activities/course/5305a8f7-943f-4647-bc69-74ccd52e9921",
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
                    "id": "http://vocab.xapi.fr/categories/moodle/forum",
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
            "http://vocab.xapi.fr/extensions/platform-event": "\\mod_forum\\event\\discussion_created"
        }
    },
    "timestamp": "2019-08-14T17:20:52+02:00"
}
```


<a name="created-post"></a>
## Created Post

This Statement is generated from the `\mod_forum\event\post_created` Moodle event.

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
        "id": "https://w3id.org/xapi/dod-isd/verbs/created"
    },
    "object": {
        "objectType": "Activity",
        "id": "http://xapi.moodle.com/xapi/activities/forum/b3192e37-6d57-4a6b-8642-b9259276440d/discussion/123/post/456",
        "definition": {
            "type": "http://id.tincanapi.com/activitytype/forum-reply",
            "name": {
                "en": "Re: Forum discution"
            },
            "description": {
                "en": "Message posted in the discussion..."
            }
        }
    },
    "context": {
        "contextActivities": {
            "parent": [
                {
                    "id": "http://xapi.moodle.com/xapi/activities/forum/21c872e3-e5fc-42ee-8f34-cc45a91ed777/discussion/123",
                    "definition": {
                        "type": "http://id.tincanapi.com/activitytype/forum-topic"
                    }
                }
            ],
            "grouping": [
                {
                    "id": "http://xapi.moodle.com/xapi/activities/forum/21c872e3-e5fc-42ee-8f34-cc45a91ed777",
                    "definition": {
                        "type": "http://vocab.xapi.fr/activities/forum"
                    }
                },
                {
                    "id": "http://xapi.moodle.com",
                    "definition": {
                        "type": "http://vocab.xapi.fr/activities/system"
                    }
                },
                {
                    "id": "http://xapi.moodle.com/xapi/activities/course/5305a8f7-943f-4647-bc69-74ccd52e9921",
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
                    "id": "http://vocab.xapi.fr/categories/moodle/forum",
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
            "http://vocab.xapi.fr/extensions/platform-event": "\\mod_forum\\event\\post_created"
        }
    },
    "timestamp": "2019-08-14T17:20:52+02:00"
}
```


# Moodle Profile: Authentication Statements

---

- [Logged-In](#logged-in)
- [Logged-Out](#logged-out)


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



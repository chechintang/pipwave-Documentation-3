## Initiate Verification Session

Used to start a verification session. The API generates a unique token which the merchant must include in the subsequent SDK calls.

**Method:** POST

**Action:** initiate-verification-session

### Request

**Format:** POST data

* action `required`: string \(32\)

| Remark | Sample |
| :--- | :--- |
| The action of this call, must be hardcoded to “initiate-verification-session” | initiate-verification-session |

---

* timestamp `required`: timestamp \(32\)

| Remark | Sample |
| :--- | :--- |
| The timestamp for this API call. | 1539677150 |

---

* api\_key `required`: string \(32\)

| Remark | Sample |
| :--- | :--- |
| Pipwave-assigned merchant’s API key. | sdvdas23t3btg34bhb |

* types\_of\_verification `required`: text

| Remark | Sample |
| :--- | :--- |
| JSON-encoded configuration of the type of verification enabled for this token, and the extra options related to the type. More details on the types of verification and their options in coming chapter. | _\(can be with or without indentation; Indentation is included in sample for readability\) <br>* See sample code snippet below_ |

```
{
    "credit-card": {
        "match_text": {
            "credit-card-first6": "552111",
            "Credit-card-last4": "5566",
        },
    },
    "identification": {
        "match_text": {
            "name": "Ali Baba",
        }
    }
}
```

---

- user_id `required`: string (32)

| Remark | Sample |
| :--- | :--- |
| The ID of the user the verification is for. | 1514333 |

---

- extra_param1: string (255)

| Remark | Sample |
| :--- | :--- |
| Any extra parameters you need pipwave to echo back when verification is done. | - |

---

- extra_param2: string (255)

| Remark | Sample |
| :--- | :--- |
| Any extra parameters you need pipwave to echo back when verification is done. | - |

---

- extra_param3: string (255)

| Remark | Sample |
| :--- | :--- |
| Any extra parameters you need pipwave to echo back when verification is done. | - |

---

- notification_url: string (255)

| Remark | Sample |
| :--- | :--- |
| The URL endpoint that pipwave will send notification to when verification is done. | - |

---

- allowed_mode: string (255)

| Remark | Sample |
| :--- | :--- |
| Comma-separated list of verification modes that is allowed in this verification. Not sending this means all modes are allowed. Refer to the appendix for a list of possible values. | livefeed, upload |

---

### Response

**Format:** JSON

* status: string (5)

| Remark | Sample |
| :--- | :--- |
| Status of the request. Refer to Types of Verifications section for more details on this, and appendix for list of possible values. | 200 |

---

- message: string (255)

| Remark | Sample |
| :--- | :--- |
| Error message, if any | - |

---

- token: string (32)

| Remark | Sample |
| :--- | :--- |
| Verification session token. Used in SDK. | p5nrUZol |

---

- redirect_url: key-value

| Remark | Sample |
| :--- | :--- |
| The next redirect url to the HPP solution, if needed. The URLs will be contained in key-value form, with key being the type of verification, and the value is the URL itself. | _* See sample code snippet below_ |

```
{
    "credit-card": "https://secure.pipwave.com/the/url"
}
```

### Signature

The data involved in generating the signature for this API are:
- timestamp
- action
- api_key
- user_id
- extra_param1
- extra_param2
- extra_param3
- notification_url




















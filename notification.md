# Notification

When the user verifies their document \(regardless of if success or fail\), a notification will be sent to the notification\_url that was sent in initiate-verification-session API. The notification must be responded with an “OK” message from the target URL; A fallback mechanism will send the notification every 5 minutes until the target URL responds with “OK”.

**Method:** POST

### Request

**Format:** JSON

* session\_token: string \(32\)

| Remark | Sample |
| :--- | :--- |
| The token that was initiated for this session. | p5nrUZol |

---

* verification\_type: string \(32\)

| Remark | Sample |
| :--- | :--- |
| The type of verification, refer to Types of Verifications section for more details on this, and appendix under Verification Types for valid values. | credit-card |

---

* user\_id: string \(32\)

| Remark | Sample |
| :--- | :--- |
| The user ID that was passed in to initiate this session. | 1514333 |

---

* mode: string \(32\)

| Remark | Sample |
| :--- | :--- |
| The mode the verification was done in. Refer to appendix under Verification Modes for valid values. | livefeed |

---

* attempts\_num: integer

| Remark | Sample |
| :--- | :--- |
| The number of attempts the user tried while verifying. | 1 |

---

* ip\_address: string \(64\)

| Remark | Sample |
| :--- | :--- |
| The IP address of the user. | 156.11.142.195 |

---

* user\_agent: string \(255\)

| Remark | Sample |
| :--- | :--- |
| The User agent of the user’s browser. | Mozilla\/5.0 \(Macintosh; Intel Mac OS X 10\_11\_6\) AppleWebKit\/537.36 \(KHTML, like Gecko\) Chrome\/69.0.3497.100 Safari\/537.36 |

---

* verification\_status: string \(5\)

| Remark | Sample |
| :--- | :--- |
| The result of the verification. Refer to appendix under Verification Results for valid values. | 10 |

---

* pd\_id: string \(32\)

| Remark | Sample |
| :--- | :--- |
| The unique ID generated for this document set. | PD20181016000000006 |

---

* document\_set\_scoring: float

| Remark | Sample |
| :--- | :--- |
| The AI scoring for the document set, 0 is very bad, 100 is very good. | 96.6716537476 |

---

* analysis\_result\_meta: key-value

| Remark | Sample |
| :--- | :--- |
| The meta-data result that came along with the AI analysis. Different analysis will yield different metadata. | - |

---

* extra\_param1: string \(255\)

| Remark | Sample |
| :--- | :--- |
| The extra parameter that was passed in to initiate this session. | - |

---

* extra\_param2: string \(255\)

| Remark | Sample |
| :--- | :--- |
| The extra parameter that was passed in to initiate this session. | - |

---

* extra\_param3: string \(255\)

| Remark | Sample |
| :--- | :--- |
| The extra parameter that was passed in to initiate this session. | - |

---

* documents: array

| Remark | Sample |
| :--- | :--- |
| The list of documents that was verified in this document set. | - |

---

* documents [ x ] [ document\_type ]: string \(32\)

| Remark | Sample |
| :--- | :--- |
| The type of document. Refer to appendix under Document Types for valid values. | credit-card |

---

* documents [ x ] [ subject\_filename ]: string \(255\)

| Remark | Sample |
| :--- | :--- |
| The filename of the file being analyzed. Subject means the focused image, only available if mode is “livefeed” | - |

---

* documents [ x ] [ subject\_size ]: integer

| Remark | Sample |
| :--- | :--- |
| The size of the file being analyzed. Subject means the focused image, only available if mode is “livefeed” | - |

---

* documents [ x ] [ subject\_url ]: string \(255\)

| Remark | Sample |
| :--- | :--- |
| The URL to download the file that was being analyzed. Subject means the focused image, only available if mode is “livefeed” | - |

---

* documents [ x ] [ full\_filename ]: string \(255\)

| Remark | Sample |
| :--- | :--- |
| The filename of the file being analyzed. | - |

---

* documents [ x ] [ full\_size ]: integer

| Remark | Sample |
| :--- | :--- |
| The size of the file being analyzed. | - |

---

* documents [ x ] [ full\_url ]: string \(255\)

| Remark | Sample |
| :--- | :--- |
| The URL to download the file that was being analyzed. | - |

---

* documents [ x ] [ document\_scoring ]: float

| Remark | Sample |
| :--- | :--- |
| The AI scoring for the document, 0 is very bad, 100 is very good. | 96.67 |

---

* documents [ x ] [ analysis\_result\_meta ]: key-value

| Remark | Sample |
| :--- | :--- |
| The meta-data result that came along with the AI analysis. Different analysis will yield different metadata. | - |

---

* documents [ x ] [ result ]: string \(5\)

| Remark | Sample |
| :--- | :--- |
| The result of the verification. Refer to appendix under Verification Results for valid values. | 10 |

---

* started\_at: timestamp \(32\)

| Remark | Sample |
| :--- | :--- |
| The timestamp the user started his verification process. | 1539673091 |

---

* completed\_at: timestamp \(32\)

| Remark | Sample |
| :--- | :--- |
| The timestamp the user ended his verification process. | 1539673097 |

### Signature

The data involved in generating the signature for this API are:

* timestamp
* api\_key
* pd\_id
* session\_token
* verification\_type
* user\_id
* verification\_status
* document\_set\_scoring
* api\_secret




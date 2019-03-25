## Identification Verification

Keyword: identification

Identification verification aims to verify an identification document and verify that the user indeed is the holder of the identification document via a two-set image verification. The first image is a selfie of the user, and the second image is the identification document with the holder’s picture. The faces on both images must match in order to pass the verification.

### Extra options

| Option | Description |
| :--- | :--- |
| match\_text | Texts that merchant expects to be in the document. By providing below details as part of the JSON array, the solution will the attempt to find any matches within the detected text. pipwaveDoc will return each match\_text options along with their match confidence \(0 represents no-match\) as part of notification’s analysis\_result\_meta data, under “match\_text” key. |
| match\_text.name | The name of the user |

### Matching Result

When match\_text option is used, the solution will return the result of the match\_text in the notification parameters. It will be included in the “analysis\_result\_meta” column with following format.

| Parameter | Description |
| :--- | :--- |
| match\_text | Key-value object |
| match\_text.name | If match\_text.name is provided in options, the match will be done and result will be included here, in key-value object form. |
| match\_text.name.text | The text the best match was done against |
| match\_text.name.score | The AI scoring for the match, 0 is very bad, 100 is very good. <br><br>Sample: 96.67 |
| match\_text.name.result | The result of the match. Refer to appendix under Verification Results for valid values. <br><br>Sample: 10 |




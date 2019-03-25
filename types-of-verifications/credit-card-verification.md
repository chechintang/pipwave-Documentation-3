## Credit Card Verification

Keyword: credit-card

Credit card verification aims to verify that the user has the physical credit card on hand.

### Extra options

| Option | Description |
| :--- | :--- |
| match\_text | Texts that merchant expects to be in the document. By providing below details as part of the JSON array, the solution will the attempt to find any matches within the detected text. pipwaveDoc will return each match\_text options along with their match confidence \(0 represents no-match\) as part of notification’s analysis\_result\_meta data, under “match\_text” key. |
| match\_text.credit-card-first6 | The first 6 numbers of the credit card |
| match\_text.credit-card-last4 | The last 4 numbers of the credit card |

### Matching Result

When match\_text option is used, the solution will return the result of the match\_text in the notification parameters. It will be included in the “analysis\_result\_meta” column with following format.

| Parameter | Description |
| :--- | :--- |
| match\_text | Key-value object |
| match\_text.credit-card-first6 | If match\_text.credit-card-first6 is provided in options, the match will be done and result will be included here, in key-value object form. |
| match\_text.credit-card-first6.text | The text the best match was done against |
| match\_text.credit-card-first6.score | The AI scoring for the match, 0 is very bad, 100 is very good. <br><br>Sample: 96.67 |
| match\_text.credit-card-first6.result | The result of the match. Refer to appendix under Verification Results for valid values. <br><br>Sample: 10 |
| match\_text.credit-card-last4 | If match\_text.credit-card-last4 is provided in options, the match will be done and result will be included here, in key-value object form. |
| match\_text.credit-card-last4.text | The text the best match was done against |
| match\_text.credit-card-last4.score | The AI scoring for the match, 0 is very bad, 100 is very good. <br><br>Sample: 96.67 |
| match\_text.credit-card-last4.result | The result of the match. Refer to appendix under Verification Results for valid values. <br><br>Sample: 10 |




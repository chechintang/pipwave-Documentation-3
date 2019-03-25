# JS SDK

After initiating verification session using the API detailed in [Initiate Verification Session](/initiate-verification-session.md) section, the SDK can then be used to render the verification UI and manage the verification flow. Below is the snippet of code sample to use the SDK:

```
<script src="<?php echo $sdk_url; ?>"></script>
<div id="pwdocscript"></div>
<button onclick="reqPipwave.init('pwdocscript', '<?php echo $api_key; ?>', '<?php echo $token; ?>', '<?php echo $type; ?>');">Verify doc</button>
```

The SDK URL can be found in [URL](/url.md) section, depending on the environment.

The API Key variable and token variable must be the same as the one used and obtained in the initiate-verification-session API.

The Type variable is the type of verification that is needed for the verification process. Refer to Types of Verifications section for more details on this, and appendix under Verification Types for valid values, with more added when more verification types are added to the solution.


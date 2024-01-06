# CMAnalytics
A PHP Analytics system run through Discord Webhooks.

This compact, simple, and easy-to-use analytics system has been used widely throughout my projects for a long time, so I want to release it to the public here.
CMAnalytics will automatically filter out bot/web crawler requests using a list of over 1,000 commonly found crawler User-Agents and a regex string for edge cases.

⚠️ **I am not liable for any misuse of this analytics platform such as using it to 'grab IPs' or collect other user data for malicious intent. My software is provided for educational purposes only.**

The analytics system logs the following data on each request:
* IP Address
* Country
* City
* Service Provider (ISP)
* ISP Coordinates
* Local Date & Time
* Browser Info (User-Agent)
* Any other custom data you pass in!

Example Usage:
```php
$userClickedFrom = "somePlaceYouPostedTheLink";
// Array of extra fields that will be passed into the analytics post
$extraFields = [
["name" => "Clicked from", "value" => $userClickedFrom, "inline" => true]
];

print(CMAnalyticsV2(
/* Webhook URL */
"webhookURL",
/* Webhook Name */
"Your Analytics",
/* Webhook Avatar URL */
"coolIconURL",
/* Webhook Event Name */
"Some Link Clicked",
/* Webhook Event Icon URL */
"anotherCoolIcon",
/* Webhook Color Hex */
"#ffffff",
/* Extra Webhook Fields */
$extraFields
)); // Makes the request and prints the response code of the Discord Post (200 for OK.)
```

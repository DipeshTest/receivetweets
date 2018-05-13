---
title: Twitter Listener
weight: 1
---

# Twitter Listener
This trigger activity provides your flogo application the ability to start when anyone tweets with searchString provided by user or receives tweets from particular user.This activity is developed by FLOGO AllStars team.
## Installation
### Flogo CLI
```bash
flogo install github.com/DipeshTest/receivetweets
```

### Third-party libraries used
- #### package anaconda - "github.com/ChimeraCoder/anaconda":
	Anaconda is a simple, transparent Go package for accessing version 1.1 of the Twitter API.Successful API queries return native Go structs that can be used immediately, with no need for type assertions
## Schema
Inputs and Outputs:

```json
 	"settings": [{
		"name": "apiKey",
		"type": "string",
		"required": true
	},
	{
		"name": "apiSecret",
		"type": "string",
		"required": true
	},
	{
		"name": "accessToken",
		"type": "string",
		"required": true
	},
	{
		"name": "accessTokenSecret",
		"type": "string",
		"required": true
	},
	{
		"name": "stream",
		"type": "string",
		"allowed": ["user",
		"public"],
		"value": "user",
		"required": true
	}],
	"output": [{
		"name": "tweetId",
		"type": "string"
	},
	{
		"name": "screenName",
		"type": "string"
	},
	{
		"name": "message",
		"type": "string"
	}],
	"handler": {
		"settings": [{
			"name": "searchString",
			"type": "string",
			"required": true
		}]
```
## Settings
| Setting     | Required | Description |
|:------------|:---------|:------------|
| apiKey | True     | The consumerKey of your Twitter account |         
| apiSecret   | True    | The consumerSecret of your Twitter account|
| accessToken       | True    | The accessToken of your Twitter account |
| accessTokenSecret   | True    | The accessTokenSecret of your Twitter account|
| stream   | True    | Select the stream on which trigger will listen. Possible values are "user","public"|
| searchString   | True    | Value of this field can be a string or hashtag for which you want to receive tweets. In case of stream value "user", value of this field should be users twitter account id from which you want receive tweets.|


Note: You may use below URL to generate your Twitter tokens: https://www.slickremix.com/docs/how-to-get-api-keys-and-tokens-for-twitter/
## Examples
Please refer activity_test.go 


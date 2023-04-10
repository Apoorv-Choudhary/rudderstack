# Rudderstack: Fullstack SDE-2 Assignment

## Task Description:
RudderStack lets users create sources and destinations to pull data. 
Configuration like api key, access token are required to fetch data 
from a source. In this problem we want you to develop a form builder 
for users to create a source. The user-defined configurations will 
be used to pull data from a given source.

**Sample form template for source 1**
```json
{
  "type": "source1",
  "fields": {
    "apiKey": {
      "type": "input",
      "label": "API key",
      "regexErrorMessage": "Invalid api key",
      "placeholder": "e.g: 1234asdf",
      "regex": "[a-z0-9]",
      "required": true
    },
    "useHTTP": {
      "type": "checkbox",
      "required": false,
      "label": "Enable HTTP"
    },
    "category": {
      "type": "singleSelect",
      "label": "Select category",
      "required": true,
      "options": [
        {"label": "Android", "value": "android"},
        {"label": "IOS", "value": "ios"}
      ]
    }
  }
}
```

Tasks to be done:

Backend:

1. API for RudderStack admin to add a source form template. Use this API to populate the DB with 3 templates
2. API for UI to fetch a specific form template based on the source type.
3. API for UI to create a source.

UI:

1. User should have the ability to select the source type which needs to be created
2. On selection, UI renders the template as a form for the user to fill.
3. Once the user clicks on submit button after filling the form, save the config in the DB. Make sure to handle validations.
    
**Sample config payload with all the fields**
```json
{
    "apiKey": "123qewqre",
    "useHTTP": false,
    "category": "android"
}
```

**Sample config payload with only required fields**
```json
{
	"apiKey": "123qewqre",
	"category": "android"
}
```


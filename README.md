# HelloID-Task-SA-Target-TOPdesk-ChangeCreate

## Prerequisites

- [ ] TOPdesk API Username and Key
- [ ] User-defined variables: `topdeskBaseUrl`, `topdeskApiUsername` and `topdeskApiSecret` created in your HelloID portal.

## Description

This code snippet will create an change within TOPdesk and executes the following tasks:

1. Define a hash table `$formObject`. The keys of the hash table represent the properties necessary to create an change within `TOPdesk`, while the values represent the values entered in the form.

> To view an example of the form output, please refer to the JSON code pasted below.

```json
{
    "requester": {
        "id": "40dd8b13-c8d2-4376-b21e-38ba6439ca38"
    },
    "briefDescription": "Change example",
    "request": "This an example of an change",
    "action": "Please act on this change example accordingly",
    "changeType": "extensive",
    "template": {
        "id": "6ea334d2-ed23-4dc7-aacb-406d5d45b015"
    },
    "category": "Hardware",
    "subcategory": "Smartphone",
    "externalNumber": "12345678",
    "impact": "Person",
    "benefit": "Better user experience",
    "priority": "P2"
}
```

> :exclamation: It is important to note that the names of your form fields might differ. Ensure that the `$formObject` hash table is appropriately adjusted to match your form fields.
> [See the TOPdesk API Docs page](https://developers.topdesk.com/explorer/?page=change#/Working%20as%20an%20operator/post_operatorChanges)

2. Creates authorization headers using the provided API key and secret.

3. Create an change using the: `Invoke-RestMethod` cmdlet. The hash table called: `$formObject` is passed to the body of the: `Invoke-RestMethod` cmdlet as a JSON object.
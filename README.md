# Whatsapp Business API

A simple nodejs script to send text messages to the user using whatsapp service.

---

## Setup

Before you start the project, make sure you have the whatsapp account set up. You can use this link to sign in: [https://developers.facebook.com/apps/](https://developers.facebook.com/apps/).

Once you have the  whatsapp account set up, enter the API_KEY, APP_NAME and SOURCE_MOBILE_NUMBER in [.env file](./.env.example). If using the test account, then SOURCE_MOBILE_NUMBER would be ```917834811114```.

---

## Installation
Once set up is done. Run the following command to start the server.

```shell
npm install
npm start
```

The server will run on port 3000.

---

### getTemplatesList
Api to get the list of templates available.
* Type: 'GET'
* Response OK Status: 200

---

### markUserOptIn
Api to mark user opt in for sending the whatsapp message.
* Type: 'GET'
* Content Type: 'application/json'
* Params:
  - mobileNumber: string
* Response OK Status: 200

---

### sendMediaImageMessage
Api to send image along with the caption.
* Type: 'GET'
* Content Type: 'application/json'
* Params:
  - mobileNumber: string
  - imageUrl: string(public available image url)
  - caption: string
* Response OK Status: 200

---

### sendMediaVideoMessage
Api to send video along with the caption.
* Type: 'GET'
* Content Type: 'application/json'
* Params:
  - mobileNumber: string
  - videoUrl: string(public available video url)
  - caption: string
* Response OK Status: 200

---

### sendTextMessage
Api to send text message.
* Type: 'GET'
* Content Type: 'application/json'
* Params:
  - mobileNumber: string
  - message: string(4096 characters limit)
* Response OK Status: 200

---

### sendTemplateMessage
Api to send templated text message.
* Type: 'GET'
* Content Type: 'application/json'
* Params:
  - mobileNumber: string
  - templateId: string
  - templateParams: array of string containing data for each param
  - message: string(4096 characters limit)/object
* Response OK Status: 200

---

## Bulk Scripts

Before you run the script, make sure that you have the user details in csv format having first column to be name and other column to be mobileNumber. You can take at the example file in [assets folder(/assets/contactDetails.csv)](./assets.example/usersDetails.csv.example)

### Bulk OptIn
To run the script, type
```Shell
node run bulkOptIn
```

The output of the script file will be stored in [results/bulkOptInResults.json](./results/bulkOptInResults.json.example) file.

### Bulk Send
To run the script, type
```Shell
node run bulkSend
```

The output of the script file will be stored in [results/bulkSendResults.json](./results/bulkSendResults.json.example) file.

# How to Send Email Messages from the Command Line Using AWS SES (Classic)

The following outlines how to send email messages from the command line using [AWS SES](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/ses/index.html) and the [AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-install.html).

## Using shorthand

```
aws ses send-email \
  --from "test@digitalsanctum.com" \
  --destination "ToAddresses=shane@digitalsanctum.com" \
  --message "Subject={Data=test1,Charset=utf8},Body={Text={Data=testing123,Charset=utf8},Html={Data=,Charset=utf8}}"
```  

## Using local files

```
aws ses send-email \
--from test@digitalsanctum.com \
--destination file://destination.json \
--message file://message.json
```

where `destination.json` is something like:

```
{
    "ToAddresses":["shane@digitalsanctum.com"]
}
```

and `message.json` is something like:

```
{
    "Subject": {
        "Data": "test1",
        "Charset": "utf-8"
    },
    "Body": {
        "Text": {
            "Data": "testing123",
            "Charset": "utf-8"
        }
    }
}
```

# awscli-helpers
Just some helpers to make life more pleasent using awscli.

Hard dependancy on jq.

```
[eythor@eythor-ws ~]$ sqs new tmpQueue
{
    "QueueUrl": "https://eu-west-1.queue.amazonaws.com/464786217001/tmpQueue"
}

[eythor@eythor-ws ~]$ sqs list
https://eu-west-1.queue.amazonaws.com/123412341234/eythorTest
https://eu-west-1.queue.amazonaws.com/123412341234/s3ObjectCreate
https://eu-west-1.queue.amazonaws.com/123412341234/tmpQueue

[eythor@eythor-ws ~]$ sqs filter tmp
https://eu-west-1.queue.amazonaws.com/123412341234/tmpQueue

[eythor@eythor-ws ~]$ sqs push tmp 'hello world'
{                                                                                                                             
    "MD5OfMessageBody": "5eb6123411234eeed093cb12341234acdc3",
    "MessageId": "23425c264-1234-43dd9-acdcc-5b123412344bae"     
}

[eythor@eythor-ws ~]$ sqs peek tmp   # peek does not delete msg                       
{                          
    "Messages": [
        {
            "MessageId": "23425c264-1234-43dd9-acdcc-5b123412344bae",
            "ReceiptHandle": "AQEBxYX4Af+hhJhhl1oclz7IxSdzXGDLQNStpp1hrXE/ptrjcfCMcLrM4bpP8XI7Rpu1R1dw8rO4+wFmssQC3FBhjjmg367cdA6DkLfMnP+XnIa2e34dSDPeYVH9+YxRSKzyeazd53THVZakGJA/jegKa+yvhxQKgy9KRWJox9H40BFGkKroaegEgcljEN/RjRIL/eTB5yQnYocTBP43CerM62DW4M5HNAMO1deHS7aXN/+mKk2zjbHSiAgs5esSr68lQcY4GXunz02Yjdj6GzbyOa8dn321Y5M0jojFFmi3UbttvCq0o1sWWFR0QUPI77oo7yNxFyJ6j8hF5yi85Sf2zIWZEXw2HEuhQg4XAzzq+84fWOG+FXKSBChmMHLPWURA",               
            "MD5OfBody": "5eb6123411234eeed093cb12341234acdc3",
            "Body": "hello world"
        }     
    ]                
}

[eythor@eythor-ws ~]$ sqs pull tmp  #  pull deletes message from queue
{
    "Messages": [                     
        {
            "MessageId": "23425c264-1234-43dd9-acdcc-5b123412344bae",             
            "ReceiptHandle": "AQEBxYX4Af+hhJhhl1oclz7IxSdzXGDLQNStpp1hrXE/ptrjcfCMcLrM4bpP8XI7Rpu1R1dw8rO4+wFmssQC3FBhjjmg367cdA6DkLfMnP+XnIa2e34dSDPeYVH9+YxRSKzyeazd53THVZakGJA/jegKa+yvhxQKgy9KRWJox9H40BFGkKroaegEgcljEN/RjRIL/eTB5yQnYocTBP43CerM62DW4M5HNAMO1deHS7aXN/+mKk2zjbHSiAgs5esSr68lQcY4GXunz02Yjdj6GzbyOa8dn321Y5M0jojFFmi3UbttvCq0o1sWWFR0QUPI77oo7yNxFyJ6j8hF5yi85Sf2zIWZEXw2HEuhQg4XAzzq+84fWOG+FXKSBChmMHLPWURA",                         
            "MD5OfBody": "5eb6123411234eeed093cb12341234acdc3",
            "Body": "hello world"
        }
    ]                                           
}
[eythor@eythor-ws ~]$ sqs peek eythor                                                                                         
[eythor@eythor-ws ~]$
```

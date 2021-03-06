# BatchDetectEntities<a name="API_BatchDetectEntities"></a>

Inspects the text of a batch of documents for named entities and returns information about them\. For more information about named entities, see [Detecting Entities](how-entities.md) 

## Request Syntax<a name="API_BatchDetectEntities_RequestSyntax"></a>

```
{
   "LanguageCode": "string",
   "TextList": [ "string" ]
}
```

## Request Parameters<a name="API_BatchDetectEntities_RequestParameters"></a>

For information about the parameters that are common to all actions, see Common Parameters\.

The request accepts the following data in JSON format\.

 ** LanguageCode **   
The language of the input documents\. All documents must be in the same language\.  
Type: String  
Length Constraints: Minimum length of 1\.  
Required: Yes

 ** TextList **   
A list containing the text of the input documents\. The list can contain a maximum of 25 documents\. Each document must contain fewer than 5,000 bytes of UTF\-8 encoded characters\.  
Type: Array of strings  
Length Constraints: Minimum length of 1\.  
Required: Yes

## Response Syntax<a name="API_BatchDetectEntities_ResponseSyntax"></a>

```
{
   "ErrorList": [ 
      { 
         "ErrorCode": "string",
         "ErrorMessage": "string",
         "Index": number
      }
   ],
   "ResultList": [ 
      { 
         "Entities": [ 
            { 
               "BeginOffset": number,
               "EndOffset": number,
               "Score": number,
               "Text": "string",
               "Type": "string"
            }
         ],
         "Index": number
      }
   ]
}
```

## Response Elements<a name="API_BatchDetectEntities_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The following data is returned in JSON format by the service\.

 ** ErrorList **   
A list containing one [BatchItemError](API_BatchItemError.md) object for each document that contained an error\. The results are sorted in ascending order by the `Index` field and match the order of the documents in the input list\. If there are no errors in the batch, the `ErrorList` is empty\.  
Type: Array of [BatchItemError](API_BatchItemError.md) objects

 ** ResultList **   
A list of [BatchDetectEntitiesItemResult](API_BatchDetectEntitiesItemResult.md) objects containing the results of the operation\. The results are sorted in ascending order by the `Index` field and match the order of the documents in the input list\. If all of the documents contain an error, the `ResultList` is empty\.  
Type: Array of [BatchDetectEntitiesItemResult](API_BatchDetectEntitiesItemResult.md) objects

## Errors<a name="API_BatchDetectEntities_Errors"></a>

For information about the errors that are common to all actions, see [Common Errors](CommonErrors.md)\.

 **BatchSizeLimitExceededException**   
The number of documents in the request exceeds the limit of 25\. Try your request again with fewer documents\.  
HTTP Status Code: 400

 **InternalServerException**   
An internal server error occurred\. Retry your request\.  
HTTP Status Code: 500

 **InvalidRequestException**   
The request is invalid\.  
HTTP Status Code: 400

 **TextSizeLimitExceededException**   
The size of the input text exceeds the limit\. Use a smaller document\.  
HTTP Status Code: 400

 **UnsupportedLanguageException**   
Amazon Comprehend can't process the language of the input text\. For all APIs except `DetectDominantLanguage`, Amazon Comprehend accepts only English or Spanish text\. For the `DetectDominantLanguage` API, Amazon Comprehend detects 100 languages\. For a list of languages, see [Detecting the Primary Language ](how-languages.md)   
HTTP Status Code: 400

## See Also<a name="API_BatchDetectEntities_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:

+  [AWS Command Line Interface](http://docs.aws.amazon.com/goto/aws-cli/comprehend-2017-11-27/BatchDetectEntities) 

+  [AWS SDK for \.NET](http://docs.aws.amazon.com/goto/DotNetSDKV3/comprehend-2017-11-27/BatchDetectEntities) 

+  [AWS SDK for C\+\+](http://docs.aws.amazon.com/goto/SdkForCpp/comprehend-2017-11-27/BatchDetectEntities) 

+  [AWS SDK for Go](http://docs.aws.amazon.com/goto/SdkForGoV1/comprehend-2017-11-27/BatchDetectEntities) 

+  [AWS SDK for Java](http://docs.aws.amazon.com/goto/SdkForJava/comprehend-2017-11-27/BatchDetectEntities) 

+  [AWS SDK for JavaScript](http://docs.aws.amazon.com/goto/AWSJavaScriptSDK/comprehend-2017-11-27/BatchDetectEntities) 

+  [AWS SDK for PHP V3](http://docs.aws.amazon.com/goto/SdkForPHPV3/comprehend-2017-11-27/BatchDetectEntities) 

+  [AWS SDK for Python](http://docs.aws.amazon.com/goto/boto3/comprehend-2017-11-27/BatchDetectEntities) 

+  [AWS SDK for Ruby V2](http://docs.aws.amazon.com/goto/SdkForRubyV2/comprehend-2017-11-27/BatchDetectEntities) 
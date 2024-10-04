```
 .----.   .----. .---.  .-.   
 | {}  } { {__  /  ___} | |   
 | .-. \ .-._} }\     } | `--.
 `-' `-' `----'  `---'  `----'
 Really  Short  Config  Language
```
---
 
 My own language designed to store key,data pairs as efficiently as possible. It supports every feature JSON does, but it uses a more compact syntax.
 It is NOT designed to look 'nice' or readable. Its meant to be as storage-efficient as possible.
 
 I hear you ask: why?
 The primary use case for this data format is, well, storage efficiency. We want to use the least amount of bytes possible while maintaining a string format 
 that also works with Roblox's *DataStores*.
 This is a fully functioning alternative to JSON, and it uses 10-60% characters less.

 For anything else than roblox datastores, I recommend using BSON or normal JSON instead.

 ```
    RSCL                                          JSON                                      
   ⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯    ⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯
   1'Hello world,                                 {                                         
   2:56,                                           "1": "Hello world",
   3{                                              "2": 56,
     1'Hello world 2!,                             "3": {
     2:t,                                                "1": "Hello world 2!",
     3:f,                                                "2": true,
     4{                                                  "3": false,
        1'string1}                                       "4": {
     5:12}                                                     "1": "string1"
   4:t,                                                  },
   5{                                                    "5": 12
      1'hi!,                                       },
      2{                                           "4": true,
         t,64,'string,~}}                          "5": {
   6:~                                                   "1": "hi!",
	.			    	                        "2": [
	.                                                          true,
	.                                                          64,
	.                                                          "string",
	.                                                          null
	.                                                    ]
	.	                                          },
	.                                              "6": null
	.                                             }
   ⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯    ⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯
    Character count: 96                           Character count: 161
   ⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯
   RSCL | 1'Hello world,2:56,3{1'Hello world 2!,2:t,3:f,4{1'string1}5:12}4:t,5{1'hi!,2{t,64,'string,~}}6:~
   JSON | {1":"Hello world","2":56,"3":{"1":"Hello world 2!","2":true,"3":false,"4":{"1":"string1"},"5":12},"4":true,"5":{"1":"hi!","2":[true,64,"string",null]},"6":null}
   ⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯
```


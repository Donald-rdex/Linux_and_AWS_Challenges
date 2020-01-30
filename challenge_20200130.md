**Tags: Programming, AWS, AWS Lambda, Intermediate**

Continuing on the AWS theme, create an AWS Lambda Function that given an integer json object, 
'{"gridsize": INT}', returns a json object array, {"numbergrid": [[]]}, from 0 and goes to a 
maximum of 4096, with each "side" of the grid the same number and 
counting up to the center.  It should return an "error" json string if the input is negative or 
above 4096. 

For example given:

 `{"gridsize": 3}`, return: `{"numbergrid": [[0,0,0],[0,1,0],[0,0,0]]}`

 `{"gridsize": 4}`, return: `{"numbergrid": [[0,0,0,0],[0,1,1,0],[0,1,1,0], [0,0,0,0]]}`

 `{"gridsize": 5}`, return: `{"numbergrid": [[0,0,0,0,0],[0,1,1,1,0],[0,1,2,1,0], [0,1,1,1,0], [0,0,0,0,0]]}`
 
 
Next, write a wrapper script around the 'aws lambda invoke' CLI command:
 https://docs.aws.amazon.com/cli/latest/reference/lambda/invoke.html  That allows you to specify 
 a grid size, but it returns prints it in a "nice" output.

Ex:

```$> my_grid_sizer.sh 3
Calling AWS Lambda...
Got grid:
 0 0 0
 0 1 0
 0 0 0
```

You may code the lambda solution in any language you like, see: 
https://docs.aws.amazon.com/lambda/latest/dg/lambda-runtimes.html 
Both pieces, the AWS Lambda code and the invocation script, are part of the solution to this one.

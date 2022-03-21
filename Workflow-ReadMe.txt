Workflow maven-buildPublish.yml will build a package using Maven and then publish it to GitHub packages when a release is created.

Few points considered in yaml - 

# For Tagging, it is using DEFAULT_BUMP as minor and hence create Minor release tags. I have created an environment named "Release" which have secret "ReleaseType", which can be used to generate the tags based on enviroment (Major for - releases and Minor for  patches for example).
Currently not using this environemnt based mapping. 

# We can use different environments for controlling Build/Release from different branches. 

# Currently, below tag is used to trigger the process on push to main only. 
push:
    branches: [ main ]
 
 We can also have mappings inside the Environments for same.
 
# CurrenttagVersion output from Job BuildAndPublish is used to pass tag values between jobs.


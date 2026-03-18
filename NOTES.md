Hey There,

Right now i'm experiencing my deploys failing, telling me the deploy is using Railpack. But, below in settings of the deploy, it says Docker File detected. Furthermore, there are no build command options available for me to use.

I'm thoroughly confused why I am not able to add in build commands in Railway, and why it is detecting Doctorfile when the build is leveraging Raiilpack.

## Overview 

The reason you are not able to add build commands in your Railway project is because the Railway build tool has detected Dockerfile in the root of your project folder. Once a Dockerfile is detected Railway will build your project using the Dockerfile settings. To prevent this from occurring you will need to delete the Dockerfile.

Please confirm if your project is using a Dockerfile. Here are the steps you should take
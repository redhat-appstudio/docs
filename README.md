# Red Hat App Studio 


## Onboarding

### Create an account

Sign up for AppStudio https://docs.google.com/document/d/1hFvQDH1H6MGNqTGfcZpyl2h8OIaynP8sokZohCS0Su0
and request one of the approvers to let you in.


### Run the UI

The UI isn't hosted anywhere at the moment. Therefore, you'd need to run it locally. 
Please see https://github.com/openshift/hac-dev/ for detailed steps.

:hotsprings:	**NOTE**
This step should go away once the UI is hosted on a staging environment.

## Deploy your first Application


### Build and Deploy your first Component

1. Using the wizard, create an `Application` and add a `Component` with the Git URL https://github.com/sbose78/dc-metro-map
3. Set the port to "8080" in the UI.
4. Set the resources to "200m" and "256MiB" in the UI.
5. Hit Create. 

Note, following are the port numbers to be used for the source code repositories being imported
1. https://github.com/sbose78/dc-metro-map runs on port 8080
2. https://github.com/devfile-samples/devfile-sample-code-with-quarkus runs on port 8081
3. https://github.com/devfile-samples/devfile-sample-java-springboot-basic runs on port 8081



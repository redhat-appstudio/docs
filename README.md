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

### Set up your pull secret 

For App Studio to be able to push to a registry, a pull secret needs to be configured. 
Please request Sahil Budhwar and Flavius Lacatusu to send you the pull secret which will need to created in your 
AppStudio namespace/workspace.


```
apiVersion: v1
kind: Secret
metadata:
  name: redhat-appstudio-registry-pull-secret
data:
  .dockerconfigjson: cant-say
type: kubernetes.io/dockerconfigjson
```

:hotsprings:	**NOTE**
This step should go away once the following enhancements/issues are resolved:
1. The UI enables users to configure their Quay.io location
2. [SVPI-57]( https://issues.redhat.com/browse/SVPI-57) Quay.io authentication is possible using an SPI-driven flow 
3. [build-service/pull/65](https://github.com/redhat-appstudio/application-service/pull/65) Build Service sets up the default pull secret for every user.

### Build your first Component

1. Using the wizard, create an `Application` and add a `Component` with the Git URL https://github.com/sbose78/dc-metro-map
3. Set the port to "8080" in the UI.
4. Set the resources to "200m" and "256MiB" in the UI.
5. Hit Create. 

:hotsprings:	**NOTE**
* If the `Component` appears to succeed, yet no Build gets triggered, you've most likely hit a bug <Placeholder for the UI Bug>, please recreate the `Component` with a different name.  

### Deploy your first Component

1. Find the URL to your GitOps repository in the generated `Application` CR.
2. Create the GitOpsDeployment resource(s) in your namespace/workspace as per the example https://gist.github.com/sbose78/152fdf1028fda427f9bf12e444de6311 . Replace the repo URL and path with those in your GitOps repository.

:hotsprings: **NOTE**
This step should go away once the following enhancements/issues are resolved:
1. Concept of 'environments' is introduced.
2. GitOps repository has the 'environments' directory as per the [Repository Template](https://github.com/redhat-appstudio/gitops-repository-template): [DEVHAS-87](https://issues.redhat.com/browse/DEVHAS-87).
3. GitOps Service automatically generates a `GitOpsDeployment` CR referencing the user's GitOps repository URL and the path to the 'PoC' environment.



## master first

```shell
Started by user admin
 > git rev-parse --is-inside-work-tree # timeout=10
Setting origin to https://github.com/jmyung/sample-app.git
 > git config remote.origin.url https://github.com/jmyung/sample-app.git # timeout=10
Fetching origin...
Fetching upstream changes from origin
 > git --version # timeout=10
 > git config --get remote.origin.url # timeout=10
 > git fetch --tags --progress origin +refs/heads/*:refs/remotes/origin/*
Seen branch in repository origin/master
Seen 1 remote branch
Obtained Jenkinsfile from a7e8a0791542516806a3cfc60d2ab5e46cb13d39
Running in Durability level: MAX_SURVIVABILITY
[Pipeline] podTemplate
[Pipeline] {
[Pipeline] node
Still waiting to schedule task
‘sample-app-tk6bp-25h78’ is offline
Agent sample-app-tk6bp-25h78 is provisioned from template Kubernetes Pod Template
Agent specification [Kubernetes Pod Template] (sample-app):

Running on sample-app-tk6bp-25h78 in /home/jenkins/workspace/sample-app_master
[Pipeline] {
[Pipeline] stage
[Pipeline] { (Declarative: Checkout SCM)
[Pipeline] checkout
Cloning the remote Git repository
Cloning with configured refspecs honoured and without tags
Cloning repository https://github.com/jmyung/sample-app.git
 > git init /home/jenkins/workspace/sample-app_master # timeout=10
Fetching upstream changes from https://github.com/jmyung/sample-app.git
 > git --version # timeout=10
 > git fetch --no-tags --progress https://github.com/jmyung/sample-app.git +refs/heads/*:refs/remotes/origin/*
 > git config remote.origin.url https://github.com/jmyung/sample-app.git # timeout=10
 > git config --add remote.origin.fetch +refs/heads/*:refs/remotes/origin/* # timeout=10
 > git config remote.origin.url https://github.com/jmyung/sample-app.git # timeout=10
Fetching without tags
Fetching upstream changes from https://github.com/jmyung/sample-app.git
 > git fetch --no-tags --progress https://github.com/jmyung/sample-app.git +refs/heads/*:refs/remotes/origin/*
Checking out Revision a7e8a0791542516806a3cfc60d2ab5e46cb13d39 (master)
 > git config core.sparsecheckout # timeout=10
 > git checkout -f a7e8a0791542516806a3cfc60d2ab5e46cb13d39
Commit message: "first commit"
First time build. Skipping changelog.
[Pipeline] }
[Pipeline] // stage
[Pipeline] withEnv
[Pipeline] {
[Pipeline] container
[Pipeline] {
[Pipeline] stage
[Pipeline] { (Test)
[Pipeline] container
[Pipeline] {
[Pipeline] sh
+ pwd
+ ln -s /home/jenkins/workspace/sample-app_master /go/src/sample-app
+ cd /go/src/sample-app
+ go test
PASS
ok  	sample-app	0.056s
[Pipeline] }
[Pipeline] // container
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Build and push image with Container Builder)
[Pipeline] container
[Pipeline] {
[Pipeline] sh
+ PYTHONUNBUFFERED=1 gcloud container builds submit -t gcr.io/REPLACE_WITH_YOUR_PROJECT_ID/gceme:master.2 .
ERROR: (gcloud.container.builds.submit) This command has been replaced with `gcloud builds`.
[Pipeline] }
[Pipeline] // container
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Deploy Canary)
Stage "Deploy Canary" skipped due to earlier failure(s)
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Deploy Production)
Stage "Deploy Production" skipped due to earlier failure(s)
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Deploy Dev)
Stage "Deploy Dev" skipped due to earlier failure(s)
[Pipeline] }
[Pipeline] // stage
[Pipeline] }
[Pipeline] // container
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // node
[Pipeline] }
[Pipeline] // podTemplate
[Pipeline] End of Pipeline
ERROR: script returned exit code 1
Finished: FAILURE
```


## 2.0 new-feature

```shell
Started by user admin
 > git rev-parse --is-inside-work-tree # timeout=10
Setting origin to https://github.com/jmyung/sample-app.git
 > git config remote.origin.url https://github.com/jmyung/sample-app.git # timeout=10
Fetching origin...
Fetching upstream changes from origin
 > git --version # timeout=10
 > git config --get remote.origin.url # timeout=10
 > git fetch --tags --progress origin +refs/heads/*:refs/remotes/origin/*
Seen branch in repository origin/master
Seen branch in repository origin/new-feature
Seen 2 remote branches
Obtained Jenkinsfile from cc94e985d812cf1095d9f515399b090b5e5f71bc
Running in Durability level: MAX_SURVIVABILITY
[Pipeline] podTemplate
[Pipeline] {
[Pipeline] node
Still waiting to schedule task
‘sample-app-j792h-n9vtv’ is offline
Agent sample-app-j792h-n9vtv is provisioned from template Kubernetes Pod Template
Agent specification [Kubernetes Pod Template] (sample-app):

Running on sample-app-j792h-n9vtv in /home/jenkins/workspace/sample-app_new-feature
[Pipeline] {
[Pipeline] stage
[Pipeline] { (Declarative: Checkout SCM)
[Pipeline] checkout
Cloning the remote Git repository
Cloning with configured refspecs honoured and without tags
Cloning repository https://github.com/jmyung/sample-app.git
 > git init /home/jenkins/workspace/sample-app_new-feature # timeout=10
Fetching upstream changes from https://github.com/jmyung/sample-app.git
 > git --version # timeout=10
 > git fetch --no-tags --progress https://github.com/jmyung/sample-app.git +refs/heads/*:refs/remotes/origin/*
 > git config remote.origin.url https://github.com/jmyung/sample-app.git # timeout=10
 > git config --add remote.origin.fetch +refs/heads/*:refs/remotes/origin/* # timeout=10
 > git config remote.origin.url https://github.com/jmyung/sample-app.git # timeout=10
Fetching without tags
Fetching upstream changes from https://github.com/jmyung/sample-app.git
 > git fetch --no-tags --progress https://github.com/jmyung/sample-app.git +refs/heads/*:refs/remotes/origin/*
Checking out Revision cc94e985d812cf1095d9f515399b090b5e5f71bc (new-feature)
 > git config core.sparsecheckout # timeout=10
 > git checkout -f cc94e985d812cf1095d9f515399b090b5e5f71bc
Commit message: "ver 2.2.1"
 > git rev-list --no-walk 6a7167c93bfa67220469662719bba068819ccf0a # timeout=10
[Pipeline] }
[Pipeline] // stage
[Pipeline] withEnv
[Pipeline] {
[Pipeline] container
[Pipeline] {
[Pipeline] stage
[Pipeline] { (Test)
[Pipeline] container
[Pipeline] {
[Pipeline] sh
+ pwd
+ ln -s /home/jenkins/workspace/sample-app_new-feature /go/src/sample-app
+ cd /go/src/sample-app
+ go test
PASS
ok  	sample-app	0.051s
[Pipeline] }
[Pipeline] // container
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Build and push image with Container Builder)
[Pipeline] container
[Pipeline] {
[Pipeline] sh
+ PYTHONUNBUFFERED=1 gcloud builds submit -t gcr.io/qwiklabs-gcp-cd0cab18558dedf7/gceme:new-feature.5 .
Creating temporary tarball archive of 31 file(s) totalling 77.3 KiB before compression.
Uploading tarball of [.] to [gs://qwiklabs-gcp-cd0cab18558dedf7_cloudbuild/source/1542468699.97-dcf1c3c5723f43358f969d9996d59a8f.tgz]
Created [https://cloudbuild.googleapis.com/v1/projects/qwiklabs-gcp-cd0cab18558dedf7/builds/43b082dd-c94c-4096-b27f-b886be426d6a].
Logs are available at [https://console.cloud.google.com/gcr/builds/43b082dd-c94c-4096-b27f-b886be426d6a?project=101840867921].
----------------------------- REMOTE BUILD OUTPUT ------------------------------
starting build "43b082dd-c94c-4096-b27f-b886be426d6a"

FETCHSOURCE
Fetching storage object: gs://qwiklabs-gcp-cd0cab18558dedf7_cloudbuild/source/1542468699.97-dcf1c3c5723f43358f969d9996d59a8f.tgz#1542468700889674
Copying gs://qwiklabs-gcp-cd0cab18558dedf7_cloudbuild/source/1542468699.97-dcf1c3c5723f43358f969d9996d59a8f.tgz#1542468700889674...
/ [0 files][    0.0 B/ 22.4 KiB]                                                
/ [1 files][ 22.4 KiB/ 22.4 KiB]                                                
Operation completed over 1 objects/22.4 KiB.                                     
BUILD
Already have image (with digest): gcr.io/cloud-builders/docker
Sending build context to Docker daemon  111.6kB

Step 1/5 : FROM golang:1.10
1.10: Pulling from library/golang
54f7e8ac135a: Already exists
d6341e30912f: Already exists
087a57faf949: Already exists
5d71636fb824: Already exists
f368dba6a331: Already exists
1ea0c245e5c5: Pulling fs layer
f81588ba3d2a: Pulling fs layer
f81588ba3d2a: Verifying Checksum
f81588ba3d2a: Download complete
1ea0c245e5c5: Verifying Checksum
1ea0c245e5c5: Download complete
1ea0c245e5c5: Pull complete
f81588ba3d2a: Pull complete
Digest: sha256:fb6191999116434901111980421e7e2583f697e04d80ebf8256d9d3acdae17b0
Status: Downloaded newer image for golang:1.10
 ---> 0a19f4d16598
Step 2/5 : WORKDIR /go/src/app
 ---> Running in 60c2f483a871
Removing intermediate container 60c2f483a871
 ---> f9f101f93733
Step 3/5 : COPY . .
 ---> 64359f2e2ed8
Step 4/5 : RUN go install -v
 ---> Running in c5814c68fcf0
[91mapp/vendor/golang.org/x/net/context
[0m[91mapp/vendor/golang.org/x/net/context/ctxhttp
[0m[91mapp/vendor/cloud.google.com/go/compute/metadata
[0m[91mapp
[0mRemoving intermediate container c5814c68fcf0
 ---> 5bd006161b37
Step 5/5 : CMD ["app"]
 ---> Running in 3829f8042a7a
Removing intermediate container 3829f8042a7a
 ---> f63d80b02cab
Successfully built f63d80b02cab
Successfully tagged gcr.io/qwiklabs-gcp-cd0cab18558dedf7/gceme:new-feature.5
PUSH
Pushing gcr.io/qwiklabs-gcp-cd0cab18558dedf7/gceme:new-feature.5
The push refers to repository [gcr.io/qwiklabs-gcp-cd0cab18558dedf7/gceme]
6eb03e9310cc: Preparing
d5d9a871bdd5: Preparing
9fd067d7a9f8: Preparing
5ac1f8687bc7: Preparing
bc6e2262dca4: Preparing
e7b9eaeca217: Preparing
f75e64f96dbc: Preparing
8f7ee6d76fd9: Preparing
c23711a84ad4: Preparing
90d1009ce6fe: Preparing
e7b9eaeca217: Waiting
f75e64f96dbc: Waiting
8f7ee6d76fd9: Waiting
c23711a84ad4: Waiting
90d1009ce6fe: Waiting
9fd067d7a9f8: Pushed
d5d9a871bdd5: Pushed
e7b9eaeca217: Layer already exists
6eb03e9310cc: Pushed
f75e64f96dbc: Layer already exists
5ac1f8687bc7: Pushed
8f7ee6d76fd9: Layer already exists
90d1009ce6fe: Layer already exists
c23711a84ad4: Layer already exists
bc6e2262dca4: Pushed
new-feature.5: digest: sha256:a662b2c3ee74b92210816554ca66092ff80675b80b72a6b104452eb8a202d673 size: 2422
DONE
--------------------------------------------------------------------------------

ID                                    CREATE_TIME                DURATION  SOURCE                                                                                                   IMAGES                                                    STATUS
43b082dd-c94c-4096-b27f-b886be426d6a  2018-11-17T15:31:41+00:00  51S       gs://qwiklabs-gcp-cd0cab18558dedf7_cloudbuild/source/1542468699.97-dcf1c3c5723f43358f969d9996d59a8f.tgz  gcr.io/qwiklabs-gcp-cd0cab18558dedf7/gceme:new-feature.5  SUCCESS
[Pipeline] }
[Pipeline] // container
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Deploy Canary)
Stage "Deploy Canary" skipped due to when conditional
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Deploy Production)
Stage "Deploy Production" skipped due to when conditional
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Deploy Dev)
[Pipeline] container
[Pipeline] {
[Pipeline] sh
+ kubectl get ns new-feature
Error from server (NotFound): namespaces "new-feature" not found
+ kubectl create ns new-feature
namespace "new-feature" created
[Pipeline] sh
+ sed -i.bak s#LoadBalancer#ClusterIP# ./k8s/services/frontend.yaml
[Pipeline] sh
+ sed -i.bak s#gcr.io/cloud-solutions-images/gceme:1.0.0#gcr.io/qwiklabs-gcp-cd0cab18558dedf7/gceme:new-feature.5# ./k8s/dev/backend-dev.yaml ./k8s/dev/frontend-dev.yaml
[Pipeline] sh
+ kubectl --namespace=new-feature apply -f k8s/services/
service "gceme-backend" created
service "gceme-frontend" created
[Pipeline] sh
+ kubectl --namespace=new-feature apply -f k8s/dev/
deployment.extensions "gceme-backend-dev" created
resourcequota "default" created
deployment.extensions "gceme-frontend-dev" created
[Pipeline] echo
To access your environment run `kubectl proxy`
[Pipeline] echo
Then access your service via http://localhost:8001/api/v1/proxy/namespaces/new-feature/services/gceme-frontend:80/
[Pipeline] }
[Pipeline] // container
[Pipeline] }
[Pipeline] // stage
[Pipeline] }
[Pipeline] // container
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // node
[Pipeline] }
[Pipeline] // podTemplate
[Pipeline] End of Pipeline
Finished: SUCCESS
```


## canary
```shell
Branch indexing
 > git rev-parse --is-inside-work-tree # timeout=10
Setting origin to https://github.com/jmyung/sample-app.git
 > git config remote.origin.url https://github.com/jmyung/sample-app.git # timeout=10
Fetching origin...
Fetching upstream changes from origin
 > git --version # timeout=10
 > git config --get remote.origin.url # timeout=10
 > git fetch --tags --progress origin +refs/heads/*:refs/remotes/origin/*
Seen branch in repository origin/canary
Seen branch in repository origin/master
Seen branch in repository origin/new-feature
Seen 3 remote branches
Obtained Jenkinsfile from cc94e985d812cf1095d9f515399b090b5e5f71bc
Running in Durability level: MAX_SURVIVABILITY
[Pipeline] podTemplate
[Pipeline] {
[Pipeline] node
Still waiting to schedule task
‘sample-app-vprmf-csrmn’ is offline
Agent sample-app-vprmf-csrmn is provisioned from template Kubernetes Pod Template
Agent specification [Kubernetes Pod Template] (sample-app):

Running on sample-app-vprmf-csrmn in /home/jenkins/workspace/sample-app_canary
[Pipeline] {
[Pipeline] stage
[Pipeline] { (Declarative: Checkout SCM)
[Pipeline] checkout
Cloning the remote Git repository
Cloning with configured refspecs honoured and without tags
Cloning repository https://github.com/jmyung/sample-app.git
 > git init /home/jenkins/workspace/sample-app_canary # timeout=10
Fetching upstream changes from https://github.com/jmyung/sample-app.git
 > git --version # timeout=10
 > git fetch --no-tags --progress https://github.com/jmyung/sample-app.git +refs/heads/*:refs/remotes/origin/*
 > git config remote.origin.url https://github.com/jmyung/sample-app.git # timeout=10
 > git config --add remote.origin.fetch +refs/heads/*:refs/remotes/origin/* # timeout=10
 > git config remote.origin.url https://github.com/jmyung/sample-app.git # timeout=10
Fetching without tags
Fetching upstream changes from https://github.com/jmyung/sample-app.git
 > git fetch --no-tags --progress https://github.com/jmyung/sample-app.git +refs/heads/*:refs/remotes/origin/*
Checking out Revision cc94e985d812cf1095d9f515399b090b5e5f71bc (canary)
 > git config core.sparsecheckout # timeout=10
 > git checkout -f cc94e985d812cf1095d9f515399b090b5e5f71bc
Commit message: "ver 2.2.1"
First time build. Skipping changelog.
[Pipeline] }
[Pipeline] // stage
[Pipeline] withEnv
[Pipeline] {
[Pipeline] container
[Pipeline] {
[Pipeline] stage
[Pipeline] { (Test)
[Pipeline] container
[Pipeline] {
[Pipeline] sh
+ pwd
+ ln -s /home/jenkins/workspace/sample-app_canary /go/src/sample-app
+ cd /go/src/sample-app
+ go test
PASS
ok  	sample-app	0.049s
[Pipeline] }
[Pipeline] // container
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Build and push image with Container Builder)
[Pipeline] container
[Pipeline] {
[Pipeline] sh
+ PYTHONUNBUFFERED=1 gcloud builds submit -t gcr.io/qwiklabs-gcp-cd0cab18558dedf7/gceme:canary.1 .
Creating temporary tarball archive of 31 file(s) totalling 77.3 KiB before compression.
Uploading tarball of [.] to [gs://qwiklabs-gcp-cd0cab18558dedf7_cloudbuild/source/1542469111.43-e3f0b11b3cd3427f9ec7663c06c7f6b2.tgz]
Created [https://cloudbuild.googleapis.com/v1/projects/qwiklabs-gcp-cd0cab18558dedf7/builds/d787e972-4d46-4bb0-9c4b-ade021eb0193].
Logs are available at [https://console.cloud.google.com/gcr/builds/d787e972-4d46-4bb0-9c4b-ade021eb0193?project=101840867921].
----------------------------- REMOTE BUILD OUTPUT ------------------------------
starting build "d787e972-4d46-4bb0-9c4b-ade021eb0193"

FETCHSOURCE
Fetching storage object: gs://qwiklabs-gcp-cd0cab18558dedf7_cloudbuild/source/1542469111.43-e3f0b11b3cd3427f9ec7663c06c7f6b2.tgz#1542469112061204
Copying gs://qwiklabs-gcp-cd0cab18558dedf7_cloudbuild/source/1542469111.43-e3f0b11b3cd3427f9ec7663c06c7f6b2.tgz#1542469112061204...
/ [0 files][    0.0 B/ 22.4 KiB]                                                
/ [1 files][ 22.4 KiB/ 22.4 KiB]                                                
Operation completed over 1 objects/22.4 KiB.                                     
BUILD
Already have image (with digest): gcr.io/cloud-builders/docker
Sending build context to Docker daemon  111.6kB

Step 1/5 : FROM golang:1.10
1.10: Pulling from library/golang
54f7e8ac135a: Already exists
d6341e30912f: Already exists
087a57faf949: Already exists
5d71636fb824: Already exists
f368dba6a331: Already exists
1ea0c245e5c5: Pulling fs layer
f81588ba3d2a: Pulling fs layer
f81588ba3d2a: Verifying Checksum
f81588ba3d2a: Download complete
1ea0c245e5c5: Verifying Checksum
1ea0c245e5c5: Download complete
1ea0c245e5c5: Pull complete
f81588ba3d2a: Pull complete
Digest: sha256:fb6191999116434901111980421e7e2583f697e04d80ebf8256d9d3acdae17b0
Status: Downloaded newer image for golang:1.10
 ---> 0a19f4d16598
Step 2/5 : WORKDIR /go/src/app
 ---> Running in 37c0e23e5a60
Removing intermediate container 37c0e23e5a60
 ---> 3840ceb4dd8c
Step 3/5 : COPY . .
 ---> 1e5a94ecab21
Step 4/5 : RUN go install -v
 ---> Running in 14f4ab2685cd
[91mapp/vendor/golang.org/x/net/context
[0m[91mapp/vendor/golang.org/x/net/context/ctxhttp
[0m[91mapp/vendor/cloud.google.com/go/compute/metadata
[0m[91mapp
[0mRemoving intermediate container 14f4ab2685cd
 ---> b5d57f50f433
Step 5/5 : CMD ["app"]
 ---> Running in 91edcf989cdb
Removing intermediate container 91edcf989cdb
 ---> e25abfbc115f
Successfully built e25abfbc115f
Successfully tagged gcr.io/qwiklabs-gcp-cd0cab18558dedf7/gceme:canary.1
PUSH
Pushing gcr.io/qwiklabs-gcp-cd0cab18558dedf7/gceme:canary.1
The push refers to repository [gcr.io/qwiklabs-gcp-cd0cab18558dedf7/gceme]
f11f9bf8f5d0: Preparing
c05d44437015: Preparing
14b5853f4310: Preparing
5ac1f8687bc7: Preparing
bc6e2262dca4: Preparing
e7b9eaeca217: Preparing
f75e64f96dbc: Preparing
8f7ee6d76fd9: Preparing
c23711a84ad4: Preparing
90d1009ce6fe: Preparing
e7b9eaeca217: Waiting
f75e64f96dbc: Waiting
8f7ee6d76fd9: Waiting
c23711a84ad4: Waiting
90d1009ce6fe: Waiting
5ac1f8687bc7: Layer already exists
bc6e2262dca4: Layer already exists
e7b9eaeca217: Layer already exists
f75e64f96dbc: Layer already exists
8f7ee6d76fd9: Layer already exists
c23711a84ad4: Layer already exists
90d1009ce6fe: Layer already exists
14b5853f4310: Pushed
c05d44437015: Pushed
f11f9bf8f5d0: Pushed
canary.1: digest: sha256:f2054b7ad2e01e2366d7fdbc89f4b2365f6528761134d4bfbdd3324d4cdf2911 size: 2422
DONE
--------------------------------------------------------------------------------

ID                                    CREATE_TIME                DURATION  SOURCE                                                                                                   IMAGES                                               STATUS
d787e972-4d46-4bb0-9c4b-ade021eb0193  2018-11-17T15:38:32+00:00  26S       gs://qwiklabs-gcp-cd0cab18558dedf7_cloudbuild/source/1542469111.43-e3f0b11b3cd3427f9ec7663c06c7f6b2.tgz  gcr.io/qwiklabs-gcp-cd0cab18558dedf7/gceme:canary.1  SUCCESS
[Pipeline] }
[Pipeline] // container
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Deploy Canary)
[Pipeline] container
[Pipeline] {
[Pipeline] sh
+ sed -i.bak s#gcr.io/cloud-solutions-images/gceme:1.0.0#gcr.io/qwiklabs-gcp-cd0cab18558dedf7/gceme:canary.1# ./k8s/canary/backend-canary.yaml ./k8s/canary/frontend-canary.yaml
[Pipeline] sh
+ kubectl --namespace=production apply -f k8s/services/
service "gceme-backend" unchanged
service "gceme-frontend" unchanged
[Pipeline] sh
+ kubectl --namespace=production apply -f k8s/canary/
deployment.extensions "gceme-backend-canary" configured
deployment.extensions "gceme-frontend-canary" configured
[Pipeline] sh
+ kubectl --namespace=production get service/gceme-frontend -o jsonpath={.status.loadBalancer.ingress[0].ip}
+ echo http://104.198.172.96
[Pipeline] }
[Pipeline] // container
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Deploy Production)
Stage "Deploy Production" skipped due to when conditional
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Deploy Dev)
Stage "Deploy Dev" skipped due to when conditional
[Pipeline] }
[Pipeline] // stage
[Pipeline] }
[Pipeline] // container
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // node
[Pipeline] }
[Pipeline] // podTemplate
[Pipeline] End of Pipeline
Finished: SUCCESS
```

## deploy to production

```
[~/dev/continuous-deployment-on-kubernetes/sample-app]$ git checkout master
Switched to branch 'master'
Your branch is up-to-date with 'origin/master'.
[~/dev/continuous-deployment-on-kubernetes/sample-app]$
[~/dev/continuous-deployment-on-kubernetes/sample-app]$ git merge canary
Updating a7e8a07..cc94e98
Fast-forward
 Jenkinsfile | 14 +++++++-------
 html.go     |  2 +-
 main.go     |  2 +-
 3 files changed, 9 insertions(+), 9 deletions(-)
[~/dev/continuous-deployment-on-kubernetes/sample-app]$
[~/dev/continuous-deployment-on-kubernetes/sample-app]$ git push origin master
Total 0 (delta 0), reused 0 (delta 0)
To https://github.com/jmyung/sample-app.git
   a7e8a07..cc94e98  master -> master
```


## master

```shell
Branch indexing
 > git rev-parse --is-inside-work-tree # timeout=10
Setting origin to https://github.com/jmyung/sample-app.git
 > git config remote.origin.url https://github.com/jmyung/sample-app.git # timeout=10
Fetching origin...
Fetching upstream changes from origin
 > git --version # timeout=10
 > git config --get remote.origin.url # timeout=10
 > git fetch --tags --progress origin +refs/heads/*:refs/remotes/origin/*
Seen branch in repository origin/canary
Seen branch in repository origin/master
Seen branch in repository origin/new-feature
Seen 3 remote branches
Obtained Jenkinsfile from cc94e985d812cf1095d9f515399b090b5e5f71bc
Running in Durability level: MAX_SURVIVABILITY
[Pipeline] podTemplate
[Pipeline] {
[Pipeline] node
Still waiting to schedule task
‘sample-app-q7c61-bsxrd’ is offline
Agent sample-app-q7c61-bsxrd is provisioned from template Kubernetes Pod Template
Agent specification [Kubernetes Pod Template] (sample-app):

Running on sample-app-q7c61-bsxrd in /home/jenkins/workspace/sample-app_master
[Pipeline] {
[Pipeline] stage
[Pipeline] { (Declarative: Checkout SCM)
[Pipeline] checkout
Cloning the remote Git repository
Cloning with configured refspecs honoured and without tags
Cloning repository https://github.com/jmyung/sample-app.git
 > git init /home/jenkins/workspace/sample-app_master # timeout=10
Fetching upstream changes from https://github.com/jmyung/sample-app.git
 > git --version # timeout=10
 > git fetch --no-tags --progress https://github.com/jmyung/sample-app.git +refs/heads/*:refs/remotes/origin/*
 > git config remote.origin.url https://github.com/jmyung/sample-app.git # timeout=10
 > git config --add remote.origin.fetch +refs/heads/*:refs/remotes/origin/* # timeout=10
 > git config remote.origin.url https://github.com/jmyung/sample-app.git # timeout=10
Fetching without tags
Fetching upstream changes from https://github.com/jmyung/sample-app.git
 > git fetch --no-tags --progress https://github.com/jmyung/sample-app.git +refs/heads/*:refs/remotes/origin/*
Checking out Revision cc94e985d812cf1095d9f515399b090b5e5f71bc (master)
 > git config core.sparsecheckout # timeout=10
 > git checkout -f cc94e985d812cf1095d9f515399b090b5e5f71bc
Commit message: "ver 2.2.1"
 > git rev-list --no-walk a7e8a0791542516806a3cfc60d2ab5e46cb13d39 # timeout=10
[Pipeline] }
[Pipeline] // stage
[Pipeline] withEnv
[Pipeline] {
[Pipeline] container
[Pipeline] {
[Pipeline] stage
[Pipeline] { (Test)
[Pipeline] container
[Pipeline] {
[Pipeline] sh
+ pwd
+ ln -s /home/jenkins/workspace/sample-app_master /go/src/sample-app
+ cd /go/src/sample-app
+ go test
PASS
ok  	sample-app	0.054s
[Pipeline] }
[Pipeline] // container
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Build and push image with Container Builder)
[Pipeline] container
[Pipeline] {
[Pipeline] sh
+ PYTHONUNBUFFERED=1 gcloud builds submit -t gcr.io/qwiklabs-gcp-cd0cab18558dedf7/gceme:master.3 .
Creating temporary tarball archive of 31 file(s) totalling 77.3 KiB before compression.
Uploading tarball of [.] to [gs://qwiklabs-gcp-cd0cab18558dedf7_cloudbuild/source/1542469471.65-b01024f57777414d904accbb1235e478.tgz]
Created [https://cloudbuild.googleapis.com/v1/projects/qwiklabs-gcp-cd0cab18558dedf7/builds/1df8175c-5017-4753-9b05-b822bd882aca].
Logs are available at [https://console.cloud.google.com/gcr/builds/1df8175c-5017-4753-9b05-b822bd882aca?project=101840867921].
----------------------------- REMOTE BUILD OUTPUT ------------------------------
starting build "1df8175c-5017-4753-9b05-b822bd882aca"

FETCHSOURCE
Fetching storage object: gs://qwiklabs-gcp-cd0cab18558dedf7_cloudbuild/source/1542469471.65-b01024f57777414d904accbb1235e478.tgz#1542469472329542
Copying gs://qwiklabs-gcp-cd0cab18558dedf7_cloudbuild/source/1542469471.65-b01024f57777414d904accbb1235e478.tgz#1542469472329542...
/ [0 files][    0.0 B/ 22.4 KiB]                                                
/ [1 files][ 22.4 KiB/ 22.4 KiB]                                                
Operation completed over 1 objects/22.4 KiB.                                     
BUILD
Already have image (with digest): gcr.io/cloud-builders/docker
Sending build context to Docker daemon  111.6kB

Step 1/5 : FROM golang:1.10
1.10: Pulling from library/golang
54f7e8ac135a: Already exists
d6341e30912f: Already exists
087a57faf949: Already exists
5d71636fb824: Already exists
f368dba6a331: Already exists
1ea0c245e5c5: Pulling fs layer
f81588ba3d2a: Pulling fs layer
f81588ba3d2a: Verifying Checksum
f81588ba3d2a: Download complete
1ea0c245e5c5: Verifying Checksum
1ea0c245e5c5: Download complete
1ea0c245e5c5: Pull complete
f81588ba3d2a: Pull complete
Digest: sha256:fb6191999116434901111980421e7e2583f697e04d80ebf8256d9d3acdae17b0
Status: Downloaded newer image for golang:1.10
 ---> 0a19f4d16598
Step 2/5 : WORKDIR /go/src/app
 ---> Running in d24651b0661c
Removing intermediate container d24651b0661c
 ---> 6fd0e2e624d2
Step 3/5 : COPY . .
 ---> c96f3978f003
Step 4/5 : RUN go install -v
 ---> Running in 0503f69225b5
[91mapp/vendor/golang.org/x/net/context
[0m[91mapp/vendor/golang.org/x/net/context/ctxhttp
[0m[91mapp/vendor/cloud.google.com/go/compute/metadata
[0m[91mapp
[0mRemoving intermediate container 0503f69225b5
 ---> 912643427632
Step 5/5 : CMD ["app"]
 ---> Running in 3458431ab1f5
Removing intermediate container 3458431ab1f5
 ---> cd1d9ea2d497
Successfully built cd1d9ea2d497
Successfully tagged gcr.io/qwiklabs-gcp-cd0cab18558dedf7/gceme:master.3
PUSH
Pushing gcr.io/qwiklabs-gcp-cd0cab18558dedf7/gceme:master.3
The push refers to repository [gcr.io/qwiklabs-gcp-cd0cab18558dedf7/gceme]
19735d590b3e: Preparing
53563f75423f: Preparing
a98b8d027b4c: Preparing
5ac1f8687bc7: Preparing
bc6e2262dca4: Preparing
e7b9eaeca217: Preparing
f75e64f96dbc: Preparing
8f7ee6d76fd9: Preparing
c23711a84ad4: Preparing
90d1009ce6fe: Preparing
e7b9eaeca217: Waiting
f75e64f96dbc: Waiting
8f7ee6d76fd9: Waiting
c23711a84ad4: Waiting
90d1009ce6fe: Waiting
bc6e2262dca4: Layer already exists
5ac1f8687bc7: Layer already exists
e7b9eaeca217: Layer already exists
f75e64f96dbc: Layer already exists
c23711a84ad4: Layer already exists
8f7ee6d76fd9: Layer already exists
90d1009ce6fe: Layer already exists
a98b8d027b4c: Pushed
53563f75423f: Pushed
19735d590b3e: Pushed
master.3: digest: sha256:244edecdcd9e8094738702e1442679bf7ab43a01348a3842abc3154346a577f9 size: 2422
DONE
--------------------------------------------------------------------------------

ID                                    CREATE_TIME                DURATION  SOURCE                                                                                                   IMAGES                                               STATUS
1df8175c-5017-4753-9b05-b822bd882aca  2018-11-17T15:44:32+00:00  29S       gs://qwiklabs-gcp-cd0cab18558dedf7_cloudbuild/source/1542469471.65-b01024f57777414d904accbb1235e478.tgz  gcr.io/qwiklabs-gcp-cd0cab18558dedf7/gceme:master.3  SUCCESS
[Pipeline] }
[Pipeline] // container
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Deploy Canary)
Stage "Deploy Canary" skipped due to when conditional
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Deploy Production)
[Pipeline] container
[Pipeline] {
[Pipeline] sh
+ sed -i.bak s#gcr.io/cloud-solutions-images/gceme:1.0.0#gcr.io/qwiklabs-gcp-cd0cab18558dedf7/gceme:master.3# ./k8s/production/backend-production.yaml ./k8s/production/frontend-production.yaml
[Pipeline] sh
+ kubectl --namespace=production apply -f k8s/services/
service "gceme-backend" unchanged
service "gceme-frontend" unchanged
[Pipeline] sh
+ kubectl --namespace=production apply -f k8s/production/
deployment.extensions "gceme-backend-production" configured
deployment.extensions "gceme-frontend-production" configured
[Pipeline] sh
+ kubectl --namespace=production get service/gceme-frontend -o jsonpath={.status.loadBalancer.ingress[0].ip}
+ echo http://104.198.172.96
[Pipeline] }
[Pipeline] // container
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Deploy Dev)
Stage "Deploy Dev" skipped due to when conditional
[Pipeline] }
[Pipeline] // stage
[Pipeline] }
[Pipeline] // container
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // node
[Pipeline] }
[Pipeline] // podTemplate
[Pipeline] End of Pipeline
Finished: SUCCESS
```

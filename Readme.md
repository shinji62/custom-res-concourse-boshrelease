### Concourse custom resource Bosh release

For big company you don't really to ask all developer to add there resource trought the pipeline
everytime.


This Bosh release will install custom resource to your default Concourse setup.




### Supported Custom Resource

* [Slack-notification](https://github.com/cloudfoundry-community/slack-notification-resource)



### Usage

In your deployment file on the worker Vm
just add
```
- release: custom-res-concourse-boshrelease
  name: slack-notification
```
like
```
- name: Worker
  azs: [z1]
  ....
  jobs:
    - release: concourse
     name: groundcrew
     properties: {drain_timeout: 10m}
    .....
    - release: custom-res-concourse-boshrelease
      name: slack-notification
```

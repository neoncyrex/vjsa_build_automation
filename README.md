# vjsa_build_automation
Build automation for vJSA instances

This is a Jenkins job which creates modified vJSA image with your own ssh-keys.

1. Stage: Syntax and Lint testing

Description:
Here we are running simple code checks for ansible scripts.

2. Stage: Build vJSA

Description:
Running an ansible playbook that deploying basic vJSA image from OpenStack Glance, creates MECHID user and uploading SSH-key file for this user from a repository.
At the last step on this stage we are making a snapshot of updated vJSA virtual machine.


3. Stage: Deploy

Description:
Running an ansible playbook that deploying updated vJSA instance with pre-configured MECHID user and ssh-key.


4. Stage: Test

Description:
Performs simple checks to ensure that updated vJSA instance works properly.

5. Stage: Approve

Description:
Approval stage, which waiting for approve from repository owner in a Jenkins.
Repository owner must login to a Jenkins and click on approve(or decline) button in a Jenkins job (robot-framework-build).

6. Stage: Publish

Description:
Downloading updated vJSA image from OpenStack to a GlusterFS storage.

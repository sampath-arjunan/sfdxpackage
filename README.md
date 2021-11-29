# sfdxPackage

**Package**


1. `sfdx auth:web:login -d -a DevHub`
2. `sfdx force:org:create -f config/project-scratch-def.json -a orgalias -d 1 -s`
3. `sfdx force:source:push`
4. `sfdx force:user:permset:assign -n GIFter`
5. `sfdx force:org:open -p lightning/n/GIFter`
6. `sfdx force:package:create -n GIFter -d "Using GIPHY to find GIFs and post to Chatter" -r force-app -t Unlocked -v DevHub`
7. `sfdx force:package:list`
8. `sfdx force:package:version:create -p GIFter -d force-app -k test1234 --wait 10 -v DevHub`

Successfully created the package version [08c08000000sY4ZAAU]. Subscriber Package Version Id: 04t08000000Y9MXAA0
Package Installation URL: https://login.salesforce.com/packaging/installPackage.apexp?p0=04t08000000Y9MXAA0


## Install and Test the Package Version in a Scratch Org

1. `sfdx force:org:create -s -f config/project-scratch-def.json`
2. `sfdx force:package:install --wait 10 --publishwait 10 --package GIFter@1.0.0-1 -k test1234 —noprompt`
3. `sfdx force:user:permset:assign -n GIFter`
4. `sfdx force:org:open -p lightning/n/GIFter`



## Install the Package Version in Your Trailhead Playground (TP)

1. `sfdx force:package:install -u MyTP --wait 10 --package GIFter@1.0.0-1 -k test1234 —noprompt`
2. `sfdx force:user:permset:assign -n GIFter -u MyTP`
3. `sfdx force:org:open -p lightning/n/GIFter -u MyTP`



## New verision generation
1. `sfdx force:package:version:create -p GIFter -d force-app -k test1234 --wait 10 -v DevHub`


## Upgrade

Scratch Org
1. `sfdx force:package:install --wait 10 --publishwait 10 --package GIFter@1.1.0-1 -k test1234 —noprompt`

## Specific Org: 

1. `sfdx force:package:install -u MyTP --wait 10 --package GIFter@1.1.0-1 -k test1234 —noprompt`

2. `sfdx force:package:version:create -p GIFter -d force-app -k test1234 --wait 10 --codecoverage -v DevHub`



## Promote the Package
1. `sfdx force:package:version:promote -p "”`



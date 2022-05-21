# warehouse.histo.fyi
The repository for the S3 bucket based warehouse which powers the website and is updated by the pipeline.

## How this works

Data is produced by the pipeline on the local machine using Minio to simulate S3 locally. 

As each action of the pipeline is performed, data accumulates locally and is committed to a version branch. 

Once the pipeline is run to completion, the branch is pulled to the master branch. At this point it is automatically deployed to the s3 bucket by the Github action in the .github folder. 

On completion of that deploy, it it is successful the release is tagged with the same version number as the branch. That release is then available as an archive.

## TODO

Automate version numbering so that the version number is visible on the website. 



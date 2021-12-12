## GitLab Pipelines

### Abstract
GitLab yaml pipeline repository with some specific use cases.
Used official documentation referenced as a comment on each yaml file.

### Folder structure

- **artifacts-cache-between-jobs**
    Pipeline sharing binaries generated on one job to the next one
- **conditional-jobs**
    Pipeline with 4 jobs with different conditionals:
    -- runs on master branch
    -- on non-master branches, and if commit message does not contain [new-feature-release] between brackets"
    -- manual push
    -- disabled job
- **docker-custom-image**
    creating custom docker image example, pushed to GitLab project registry:
    -- 1) generating a custom docker image
    -- 2) running jobs on that custom image
- **git-reference-cache**
    git reference cache ("git clone --reference") usage example, optimization passing from 50 to 8 min running time:
    -- 1) generating one custom docker image, with a full git clone on a local folder
    -- 2) using using that custom image, running a "git clone --reference" pointing to that folder
- **git-swallow-clone**
    pipeline specifing a swallow clone ("git clone --depth 1") at project and job level, optimization passing from 43 to 1 min running time
- **notification-on-failure**
    pipeline with a jobs running only on project failure, sending notification to a slack notification (by curl)
- **pipeline-include-template**
    yaml template example:
    -- 1) working like a "shared library", containing some common used commands
    -- 2) importing that shared pipeline, and refering that common parts
- **pipeline-multi-project**
    example of how to trigger one pipeline as a job from another pipeline (multi project pipeline)
- **vars-between-jobs**
    pipeline passing variable values from one job to another one, using dotnet artifacts

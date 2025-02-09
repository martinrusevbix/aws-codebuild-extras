# aws-codebuild-extras ![Build Status](https://codebuild.us-west-2.amazonaws.com/badges?uuid=eyJlbmNyeXB0ZWREYXRhIjoiUkxsV0l4UDBkWmh1Z1NIbm9wTENycVl4d1pDTTYrc1I3dzhFSlQ1QWFQdDl1Tm10NGduZklrTWVON1Vock5rOHVJV0xGYWhwT0V0cWVtMFg2WWRLTVlZPSIsIml2UGFyYW1ldGVyU3BlYyI6InhrOHdIV0FzY3Y1dmZ0SGwiLCJtYXRlcmlhbFNldFNlcmlhbCI6MX0%3D&branch=master)
Adds extra information of your AWS CodeBuild build via environment variables.

## Usage

Add the following command to the `install` or `pre_build` phase of your buildspec

    curl -fsSL https://raw.githubusercontent.com/martinrusevbix/aws-codebuild-extras/master/install >> extras.sh && . ./extras.sh

Alternatively, you can fork this repo and always point to the default branch of your fork.

You can also break the installation into two steps to improve readability.
For example in the `install` phase:
```
phases:
  install:
    commands:
      - echo Installing codebuild-extras...
      - curl -fsSL https://raw.githubusercontent.com/martinrusevbix/aws-codebuild-extras/master/install >> extras.sh
      - . ./extras.sh
```
|NAME|VALUE
|---|---|
|CI|true|
|CODEBUILDEXTRA|true|
|CODEBUILDEXTRA_GIT_AUTHOR|Committer Name|
|CODEBUILDEXTRA_GIT_AUTHOR_EMAIL|user@example.com|
|CODEBUILDEXTRA_GIT_BRANCH|branch name|
|CODEBUILDEXTRA_GIT_COMMIT|commit hash|
|CODEBUILDEXTRA_GIT_MESSAGE|commit message|
|CODEBUILDEXTRA_GIT_TAG|git tag|
|CODEBUILDEXTRA_PROJECT|project|
|CODEBUILDEXTRA_PULL_REQUEST|Pull request number|

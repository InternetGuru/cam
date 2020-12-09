
![tests badge at master](https://github.com/InternetGuru/cap/workflows/tests/badge.svg?branch=master)
![tests badge at dev](https://github.com/InternetGuru/cap/workflows/tests/badge.svg?branch=dev)

# Coding Assignment Plagiarism | CAP

> This GitLab CI project downloads GitLab repositories and checks for Java code similarities using Moss script. It includes current project (on current branch) plus all repositories distributed from its individual branches using [CAD](https://github.com/InternetGuru/cad). Files to compare are from `src/main/**/*.java`.

## Instructions

1. Navigate into the project and switch to the branch you want to include into Moss.

   - E.g. [umiami/george/csc220/matrix](https://gitlab.com/umiami/george/csc220/matrix)

1. Make sure you have your [personal access token](https://docs.gitlab.com/ee/user/profile/personal_access_tokens.html#creating-a-personal-access-token). On GitLab [set ACCESS_TOKEN variable](https://docs.gitlab.com/ee/ci/variables/#create-a-custom-variable-in-the-ui) into your root namespace.

   - E.g. into `umiami/george`

1. Add the following lines into your `.gitlab-ci.yml`. Specify Moss location URL in `CAP_MOSS` variable. You may want to select a different `measure.sh` revision. Do not modify `CAP_REVISION` variable unless you know what you're doing.

    ```
    include: 'https://raw.githubusercontent.com/InternetGuru/cap/master/gitlab-measure.yml'

    variables:
      CAP_MOSSURL: ""
      CAP_REVISION: "1"

    stages:
      - measure
    ```

1. To execute Moss plagiarism check and obtain URL with Moss results [run **measure stage** CI manually](https://docs.gitlab.com/ee/ci/pipelines/#run-a-pipeline-manually). You will find the URL with Moss results at the end of the pipeline output log.

## Suggestions

- [ ] Add BUTT tests.
- [ ] Specify branches to include/exclude.
- [ ] Modify source code location.
- [ ] Support other languages and extensions.
- [ ] Add GitHub support.

## Sources

- [Moss](https://theory.stanford.edu/~aiken/moss/)
- [Mossum: results visualization](https://github.com/hjalti/mossum)
- [How to cheat in computer science](https://github.com/genchang1234/How-to-cheat-in-computer-science-101)


![tests badge at master](https://github.com/InternetGuru/cap/workflows/tests/badge.svg?branch=master)
![tests badge at dev](https://github.com/InternetGuru/cap/workflows/tests/badge.svg?branch=dev)

# Coding Assignment Plagiarism | CAP

> This GitLab CI downloads repositories and checks for plagiarism using moss script.

## Instructions

> All project source files must be placed in `/src/main/` folder (including subfolders).

1. Make sure you have your [personal access token](https://docs.gitlab.com/ee/user/profile/personal_access_tokens.html#creating-a-personal-access-token). On GitLab [set ACCESS_TOKEN variable](https://docs.gitlab.com/ee/ci/variables/#create-a-custom-variable-in-the-ui) into your root namespace.

1. Add the following lines into your `.gitlab-ci.yml`. Specify moss location URL in `CAP_MOSS` varible. You may want to select a different `measure.sh` revision. Do not modify `CAP_REVISION` variable unless you know what you're doing.

    ```
    include: 'https://raw.githubusercontent.com/InternetGuru/cap/master/gitlab-measure.yml'

    variables:
      CAP_MOSS: "https://moss_location"
      CAP_REVISION: "1"

    stages:
      - measure
    ```

1. To execute moss plagiarism check script and obtain URL with moss results [run CI manually](https://docs.gitlab.com/ee/ci/pipelines/#run-a-pipeline-manually).

## Suggestions

- [ ] Add BUTT tests.
- [ ] Support specific projects branch.
- [ ] Support specific source code location.
- [ ] Support specific lang.
- [ ] Add GitHub support.

## Sources

- [moss](https://theory.stanford.edu/~aiken/moss/)
- [mossum: results visualization](https://github.com/hjalti/mossum)
- [how to cheat in computer science](https://github.com/genchang1234/How-to-cheat-in-computer-science-101)

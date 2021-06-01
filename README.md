# Secret Detection

While Developing applications, there might are chances that developer may unintentionally may unintentionally commit secrets and credentials to the repositories dure to which sensitive information gets exposed. So, we need to make sure that every time developer commits, the repo gets scanned.

This task uses [gitleaks](https://github.com/zricethezav/gitleaks) tool for detecting hardcoded secrets like passwords, api keys, and tokens in git repos. Gitleaks is an easy-to-use, all-in-one solution for finding secrets, past or present, in your code. It provides with some [default rulesets](https://github.com/zricethezav/gitleaks/blob/master/config/default.go). However, user is free to create rulesets as per his requirement by defining them inside .toml format file. To know how to write these config file, you can visit [this](https://github.com/zricethezav/gitleaks#rules-summary). Also, An example file is shown here. [here](https://github.com/urvashigupta7/secret_detection/blob/master/gitleaks.toml).

## Install the  `secret-detection` Task
`kubectl apply -f https://raw.githubusercontent.com/urvashigupta7/secret_detection/master/task/secret_detection.yaml`

## Install `git-clone` Task
`https://raw.githubusercontent.com/tektoncd/catalog/main/task/git-clone/0.3/git-clone.yaml`

## Create PVC,Pipeline and Pipelinerun
`https://raw.githubusercontent.com/urvashigupta7/secret_detection/master/pvc.yaml`
`https://raw.githubusercontent.com/urvashigupta7/secret_detection/master/pipeline.yaml`
`https://raw.githubusercontent.com/urvashigupta7/secret_detection/master/pipelinerun.yaml`

## Workspaces
* **source** : A Workspace containing your source directory.

## Parameters 
* **repo_path** : path to the repo to be scanned.
* **config_file_url** : url from where the config file would be fetched.
* **config_file_path** : path to config file.
* **output_format** : output_format to use. (JSON|CSV|SARIF) (default: `json`)
* **report_output_path** : path of file to save analysis report.
* **args** : args. (default: `[]`)

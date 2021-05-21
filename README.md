# Secret Detection

This task uses [gitleaks](https://github.com/zricethezav/gitleaks) tool for detecting hardcoded secrets like passwords, api keys, and tokens in git repos. Gitleaks is an easy-to-use, all-in-one solution for finding secrets, past or present, in your code.

## Install the Task
`kubectl apply -f https://raw.githubusercontent.com/urvashigupta7/secret_detection/master/task/secret_detection.yaml`

## Workspaces
* **source** : A Workspace containing your source directory.

## Parameters 
* **repo_path** : path to the repo to be scanned.
* **config_file_url** : url from where the config file would be fetched.
* **config_file_path** : path to config file.
* **output_format** : output_format to use. (JSON|CSV|SARIF) (default: `json`)
* **report_output_path** : path of file to save analysis report.
* **args** : args. (default: `[]`)

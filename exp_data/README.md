# Experiment Data

## Data Details

### `Bugtobetest`

The apk files of the apps, and the bug steps screenshots.

### `readme`

The README file of all apps. The filename is the hashed github link.

### `selected_data`

All of the issues, including the following info:

`app_name,category,github_link,issue_title,issue_description,issue_link,level,comments,bug_steps`

## Hash Calculation

To prevent naming conflicts for software with the same name but different categories, we use the hash value of the GitHub link as the file name for app-level information. For example, the readme file is named using the hash method. The algorithm is as follows:

```python
import hashlib

def hash_github_link(github_link: str):
    """
    github_link example: https://github.com/izivkov/CasioGShockPhoneSync
    """
    repo_name = github_link.split('github.com/')[-1].rstrip('/')
    hash_name = hashlib.md5(repo_name.encode()).hexdigest()[:32]
    return hash_name
```
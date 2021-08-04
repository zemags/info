```bash
# you are in master branch and checkout to the testing branch
git co testing
# branch name (template: story/PROJECT_NAME-TASK_NUMBER/feature_name) like story/PROJECT-01/new_feature_name or fix/PROJECT-02/fix_feautre_name
git co -b new_branch
# working on new_branch
# finished working on new_branch
git co testing
git merge new_branch
git co -b release/0.0.x
git tag -a v0.0.x -m "Version 0.0.x"
git push origin --tags
git push origin testing
git push origin release/0.0.x
git branch -d release/0.0.x
git branch -d new_branch
```
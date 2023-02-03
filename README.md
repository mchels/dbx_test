# dbx example repo

## Getting started
Go through these steps to start using dbx: https://docs.databricks.com/dev-tools/dbx.html#requirements
    1. `python -m pip install dbx`
    2. `databricks configure --token` (https://docs.databricks.com/dev-tools/cli/index.html#set-up-authentication)
    3. Copy the files in this repo to your own repo.
    4. Push your own repo.
    5. Add your own repo in databricks (you will need to set up access tokens in databricks for the git provider you use).
    6. Run a flat python file with `dbx-demo-job.py` with `dbx execute --cluster-id='your-cluster-id' dbx-demo-job --no-package`
    7. Run a databricks notebook with `dbx execute --cluster-id='your-cluter-id' dbx-notebook-demo-job --no-package`

Run `dbx sync repo --dest-repo dbx_test` to continuously synchronize your local copy with the
databrick copy (without using git). Be careful of edit conflicts, though. It seems to work alright
if all edits are made locally and the only thing that happens in the browser is execution of cells.
State is kept between sync, but cell output in the browser is not.
https://docs.databricks.com/dev-tools/dbx-sync.html#dbx-sync-development-workflows


## Notes
`dbx execute` cannot run a `notebook_task`. Doing
```
dbx execute --cluster-id='your-cluster-id' dbx-notebook-demo-job --no-package
```
gives
```
RuntimeError: Provided task type notebook_task is not supported in execute mode. Supported types are: [<TaskType.spark_python_task: 'spark_python_task'>, <TaskType.python_wheel_task: 'python_wheel_task'>]
```

## More resources:
1. https://stackoverflow.com/questions/73490143/how-do-i-include-and-install-test-files-in-a-wheel-and-deploy-to-databricks
2. https://github.com/smurching/dbx-example-project
3. Deployment file reference: https://dbx.readthedocs.io/en/latest/reference/deployment/
4. Databricks notebook gallery https://github.com/databricks/notebook_gallery
5. Best practices for databricks notebooks: https://github.com/databricks/notebook-best-practices
6. Build setup with poetry (and others): https://dbx.readthedocs.io/en/latest/features/build_management/
7. Difference between `dbx execute` and `dbx launch`: https://dbx.readthedocs.io/en/latest/faq/#whats-the-difference-between-dbx-execute-and-dbx-launch

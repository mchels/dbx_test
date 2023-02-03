# dbx example repo

## Getting started
Go through these steps to start using dbx: https://docs.databricks.com/dev-tools/dbx.html#requirements
    1. `python -m pip install dbx`
    2. `databricks configure --token` (https://docs.databricks.com/dev-tools/cli/index.html#set-up-authentication)
    3. Copy the files in this repo to your own repo.
    4. Push your own repo.
    5. Add your own repo in databricks (you will need to set up access tokens in databricks for the git provider you use).
    6. Run `dbx-demo-job.py` with `dbx execute --cluster-id='your-cluster-id' dbx-demo-job --no-package`


## Notes
`dbx execute` cannot run a notebook. Doing
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

# Conda


## Backup an environment

To backup an environment, my solution is to use conda clone to clone the current environment to a environment called `environment_backup`.

Sample code:

```shell
conda create --name my_env_backup --clone my_env
```

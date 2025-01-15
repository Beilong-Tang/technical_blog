# Slurm

For most model trainings, I used the slurm system from Kunshan Super Computing. It has gpus with 16GB and 32GB.

## Salloc a server

This serves convinient testing.

```shell
# allocate a 16GB server
salloc -p kshdnormal --ntasks-per-node=4 --cpus-per-task=8 --gres=dcu:4 --j inference_bltang --exclusive
# allocate a 32GB server
salloc -p kshdnormal --ntasks-per-node=4 --cpus-per-task=8 --gres=dcu:4 --j inference_bltang --exclusive
```

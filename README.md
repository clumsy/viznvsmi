# VizNvsmi
[VizTracer](https://github.com/gaogaotiantian/viztracer) plugins for NVSMI.
It is inspired by the official VizTracer plugings: [vizplugins](https://github.com/gaogaotiantian/vizplugins).

# Features
VizNvsmi currently only supports NVIDIA metrics tracking via [nvidia-smi](https://docs.nvidia.com/deploy/nvidia-smi/index.html).

# Install
The preferred way to install VizNvsmi is via pip:

```sh
pip install viznvsmi
```

# Basic Usage
VizNvsmi should be used with VizTracer.

You can use VizNvsmi and the plugin via command line:

```sh
viztracer --plugin "viznvsmi --utilization.memory --utilization.gpu -i 0 -f 50" -- my_script.py arg1 arg2
```
Where:
* `-i` - specifies GPU id
* `-f` - specifies how many samples per seconds to collect
* other flags map to NVSMI metrics, the full list is available via `nvidia-smi --help-query-gpu`

You can also add the plugin to VizTracer programmatically as described in the [official documentation](https://viztracer.readthedocs.io/en/latest/plugins.html).

Finally, VizNvsmi provides a [PyTorch Lightning Callback](https://lightning.ai/docs/pytorch/stable/extensions/callbacks.html) that can be used as part of model training.

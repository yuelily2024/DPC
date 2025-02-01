# DPC
Implementation of Dual Prototypes Contrastive Learning for Semi-supervised Medical Image Segmentation
### 1. Environment

This code has been tested with Python 3.6, PyTorch 1.8, torchvision 0.9.0, and CUDA 11.1 on Ubuntu 20.04.

Before running the code, set the `PYTHONPATH` to `pwd`:
```shell
export PYTHONPATH=$(pwd)/code:$PYTHONPATH
```

### 2. Data Preparation
| Dataset                               | URL |
|---------------------------------------|-----|
| ACDC                                  | [https://www.creatis.insa-lyon.fr/Challenge/acdc/databases.html](https://www.creatis.insa-lyon.fr/Challenge/acdc/databases.html) |
| ISIC 2018                             | [https://challenge2018.isic-archive.com/task1/](https://challenge2018.isic-archive.com/task1/) |
| PROMISE12                             | [cite https://doi.org/10.1016/j.media.2013.12.002](https://doi.org/10.1016/j.media.2013.12.002) |

### 3. Training & Testing & Evaluating

Run the following commands for training, testing and evaluating.

```shell
bash train3times_seeds_20p.sh -c 0 -t synapse -m dhc -e '' -l 3e-2 -w 0.1
```
`20p` denotes training with 20% labeled data, you can change this to `2p`, `5p`, ... for 2%, 5%, ... labeled data.

Parameters:

`-c`: use which gpu to train

`-t`: task, can be `synapse` or `amos`

`-m`: method, `dhc` is our proposed method

`-e`: name of current experiment

`-l`: learning rate

`-w`: weight of unsupervised loss





## License

This repository is released under MIT License.


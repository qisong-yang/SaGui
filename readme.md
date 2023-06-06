# SaGui

Portions of the code in sagui.py are adapted from [Safety Starter Agents](https://github.com/openai/safety-starter-agents).

**Warning:** If you want to use the SaGui algorithm in [Safety Gym](https://github.com/openai/safety-gym), make sure to install Safety Gym according to the instructions on the [Safety Gym repo](https://github.com/openai/safety-gym).

The various utilities here are copied over from [Spinning Up in Deep RL](https://github.com/openai/spinningup/tree/master/spinup/utils). 

## Installation & Operation

### Direct installation

To install this package:

```
cd /path/to/SaGui

pip install -e .
```

### Reproduce Experiments
To train the guide, run:
```
cd /path/to/sagui

python train-guide.py --env GuideENV -s SEED --cost_lim d --logger_kwargs_str '{"output_dir": "./guide"}'
```

If you want to test the two versions of SaGui with a well-trained guide, run:
```
cd /path/to/sagui

python sagui-cs.py /path/to/guide --env StudentENV -s SEED --cost_lim d --logger_kwargs_str '{"output_dir": "./xxx"}'

python sagui-ld.py /path/to/guide --env StudentENV -s SEED --cost_lim d --logger_kwargs_str '{"output_dir": "./xxx"}'
```

where we should have the guide in `/path/to/guide`.

`SEED` is the random seed (we use 0, 10, ..., 90 in the paper experiments), `d` is the real-world safety threshold, and `'{"output_dir": "./xxx"}'` indicates where to store the data. 

As to hyperparameters and experimental setup, you can refer to the paper and its Appendix.

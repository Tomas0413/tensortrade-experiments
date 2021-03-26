# TensorTrade Experiments
Experimenting with TensorTrade and RLlib

I created two almost identical Jupyer notebooks, the only two differences are reward and action schemes.

[TensorTrade - Sinewave with PBR and BSH](https://github.com/Tomas0413/tensortrade-experiments/blob/main/TensorTrade%20-%20Sinewave%20with%20PBR%20and%20BSH.ipynb) ([PDF](https://github.com/Tomas0413/tensortrade-experiments/blob/main/TensorTrade%20-%20Sinewave%20with%20PBR%20and%20BSH%20-%20Jupyter%20Notebook.pdf))

```python
# Position-based returns reward scheme
reward_scheme = PBR(price=p)

# Buy, sell, or hold action scheme
action_scheme = BSH(
    cash=cash,
    asset=asset
).attach(reward_scheme)
```

![results](https://github.com/Tomas0413/tensortrade-experiments/blob/main/pbr_bsh_results.png "Sinewave with PBR and BSH results")


[TensorTrade - Sinewave with SimpleProfit and ManagedRiskOrders](https://github.com/Tomas0413/tensortrade-experiments/blob/main/TensorTrade%20-%20Sinewave%20with%20SimpleProfit%20and%20ManagedRiskOrders.ipynb) ([PDF](https://github.com/Tomas0413/tensortrade-experiments/blob/main/TensorTrade%20-%20Sinewave%20with%20SimpleProfit%20and%20ManagedRiskOrders%20-%20Jupyter%20Notebook.pdf))

```python
# A simple reward scheme that rewards the agent for incremental increases in net worth
reward_scheme = SimpleProfit()

# A discrete action scheme that determines actions based on managing risk
action_scheme = ManagedRiskOrders()
```

![results](https://github.com/Tomas0413/tensortrade-experiments/blob/main/simpleprofit_managedriskorders_results.png "Sinewave with SimpleProfit and ManagedRiskOrders results")


TensorBoard charts are avaiabe [here](https://github.com/Tomas0413/tensortrade-experiments/blob/main/TensorBoard.pdf). 


TensorTrade and Ray versions I tried:

Locally:

```
Name: tensortrade
Version: 1.0.2.dev0
Summary: TensorTrade: A reinforcement learning library for training, evaluating, and deploying robust trading agents.
Home-page: https://github.com/tensortrade-org/tensortrade
Author: Adam King <adamjking3@gmail.com>, Matthew Brulhardt <mwbrulhardt@gmail.com>
Author-email: None
License: Apache 2.0
Location: /data/stock-insights/tensortrade/tensortrade
Requires: numpy, pandas, gym, pyyaml, stochastic, tensorflow, ipython, matplotlib, plotly
Required-by: 
```
```
Name: ray
Version: 2.0.0.dev0
Summary: Ray provides a simple, universal API for building distributed applications.
Home-page: https://github.com/ray-project/ray
Author: Ray Team
Author-email: ray-dev@googlegroups.com
License: Apache 2.0
Location: /root/anaconda3/lib/python3.8/site-packages
Requires: click, colorful, filelock, requests, aioredis, prometheus-client, aiohttp-cors, jsonschema, numpy, aiohttp, cloudpickle, msgpack, gpustat, protobuf, grpcio, colorama, opencensus, py-spy, pyyaml, redis
Required-by: 
```

On Google colab:
```
Name: tensortrade
Version: 1.0.1b0
Summary: TensorTrade: A reinforcement learning library for training, evaluating, and deploying robust trading agents.
Home-page: https://github.com/tensortrade-org/tensortrade
Author: Adam King <adamjking3@gmail.com>, Matthew Brulhardt <mwbrulhardt@gmail.com>
Author-email: None
License: Apache 2.0
Location: /usr/local/lib/python3.7/dist-packages
Requires: matplotlib, tensorflow, pyyaml, numpy, ipython, pandas, stochastic, plotly, gym
Required-by: 
```
```
Name: ray
Version: 1.2.0
Summary: Ray provides a simple, universal API for building distributed applications.
Home-page: https://github.com/ray-project/ray
Author: Ray Team
Author-email: ray-dev@googlegroups.com
License: Apache 2.0
Location: /usr/local/lib/python3.7/dist-packages
Requires: jsonschema, aiohttp, grpcio, protobuf, aioredis, click, prometheus-client, redis, py-spy, aiohttp-cors, filelock, opencensus, numpy, msgpack, requests, pyyaml, gpustat, colorama, colorful
Required-by: 
```

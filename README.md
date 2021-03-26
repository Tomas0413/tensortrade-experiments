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

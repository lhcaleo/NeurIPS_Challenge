**Dragonnet and Dragonnet+ t-reg : hyperparameter**

1. `early stopping` (use it or not)
2. `cool down`
3. `min_lr`
4. `lr`
5. `momentum`
6. `ReduceLROnPlateau`

---

# Early Stopping

- With early stopping

```
The back door adjustment result is below {'tarnet': {'baseline': 0.12504421744050617, 'targeted_regularization': 0.1191920418706454}, 'dragonnet': {'baseline': 0.12754051156209403, 'targeted_regularization': 0.14132166487134246}, 'nednet': {'baseline': 0.18165883789319032, 'targeted_regularization': 0.18931748731470793}} the tmle estimator result is this  {'tarnet': {'baseline': 0.12316339778468582, 'targeted_regularization': 0.11989218527556239}, 'dragonnet': {'baseline': 0.1224153766497898, 'targeted_regularization': 0.1246210706505555}, 'nednet': {'baseline': 0.13364663677613112, 'targeted_regularization': 0.14120976249201458}}
```

- Without early stopping

```
The back door adjustment result is below
{'tarnet': {'baseline': 0.14888323523825833, 'targeted_regularization': 0.1534664747963338}, 'dragonnet': {'baseline': 0.2489564837979316, 'targeted_regularization': 0.18225047169693231}, 'nednet': {'baseline': 0.19783116355831165, 'targeted_regularization': 0.2000626803963854}}
the tmle estimator result is this 
{'tarnet': {'baseline': 0.13099470470571364, 'targeted_regularization': 0.13523204088438642}, 'dragonnet': {'baseline': 0.2503474367612258, 'targeted_regularization': 0.15539140536235782}, 'nednet': {'baseline': 0.16415749393586487, 'targeted_regularization': 0.16146733824060974}}
```



# Cool down

本来是0 测试1, 3, 5, 10

**cooldown**: number of epochs to wait before resuming normal operation after lr has been reduced.

https://stackoverflow.com/questions/52338090/keras-callback-reducelronplateau-cooldown-parameter

cooldown = 1





cooldown = 5

```
The back door adjustment result is below
{'tarnet': {'baseline': 0.12343177526427251, 'targeted_regularization': 0.12394006500951399}, 'dragonnet': {'baseline': 0.13165469720235556, 'targeted_regularization': 0.14743933401005038}, 'nednet': {'baseline': 0.16071207250923614, 'targeted_regularization': 0.19900339091633457}}
the tmle estimator result is this 
{'tarnet': {'baseline': 0.11751605458244961, 'targeted_regularization': 0.11344281427383215}, 'dragonnet': {'baseline': 0.12358428597643822, 'targeted_regularization': 0.11439820363486713}, 'nednet': {'baseline': 0.12635505949632936, 'targeted_regularization': 0.12821561630110875}}
```




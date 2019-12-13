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

Original = 0

Test 1, 3, 5, 10

**cooldown**: number of epochs to wait before resuming normal operation after lr has been reduced.

https://stackoverflow.com/questions/52338090/keras-callback-reducelronplateau-cooldown-parameter

- cooldown = 1

```
The back door adjustment result is below
{'tarnet': {'baseline': 0.12033757763883295, 'targeted_regularization': 0.13501412196686438}, 'dragonnet': {'baseline': 0.11797475654976332, 'targeted_regularization': 0.15472632953498963}, 'nednet': {'baseline': 0.1806788469366141, 'targeted_regularization': 0.1896595273323854}}
the tmle estimator result is this 
{'tarnet': {'baseline': 0.12474572893390895, 'targeted_regularization': 0.11001276290844317}, 'dragonnet': {'baseline': 0.1215270365064941, 'targeted_regularization': 0.1201367646039978}, 'nednet': {'baseline': 0.12900751705353017, 'targeted_regularization': 0.12833875896688204}}
```

- cooldown = 3

```
The back door adjustment result is below
{'tarnet': {'baseline': 0.12260907230339946, 'targeted_regularization': 0.11969918100991855}, 'dragonnet': {'baseline': 0.11595785333094827, 'targeted_regularization': 0.10909926291049135}, 'nednet': {'baseline': 0.17782152746989946, 'targeted_regularization': 0.18548895967849674}}
the tmle estimator result is this 
{'tarnet': {'baseline': 0.11980048334181667, 'targeted_regularization': 0.11938923546714506}, 'dragonnet': {'baseline': 0.12120595720086974, 'targeted_regularization': 0.11369570912961112}, 'nednet': {'baseline': 0.12863719189764247, 'targeted_regularization': 0.13390230614003723}}
```

- cooldown = 5

```
The back door adjustment result is below
{'tarnet': {'baseline': 0.12343177526427251, 'targeted_regularization': 0.12394006500951399}, 'dragonnet': {'baseline': 0.13165469720235556, 'targeted_regularization': 0.14743933401005038}, 'nednet': {'baseline': 0.16071207250923614, 'targeted_regularization': 0.19900339091633457}}
the tmle estimator result is this 
{'tarnet': {'baseline': 0.11751605458244961, 'targeted_regularization': 0.11344281427383215}, 'dragonnet': {'baseline': 0.12358428597643822, 'targeted_regularization': 0.11439820363486713}, 'nednet': {'baseline': 0.12635505949632936, 'targeted_regularization': 0.12821561630110875}}
```

- cooldown = 10

```
The back door adjustment result is below
{'tarnet': {'baseline': 0.12640138775323334, 'targeted_regularization': 0.12702277868224127}, 'dragonnet': {'baseline': 0.12357037111272348, 'targeted_regularization': 0.12791702545998354}, 'nednet': {'baseline': 0.17501701868311093, 'targeted_regularization': 0.17756259224951132}}
the tmle estimator result is this 
{'tarnet': {'baseline': 0.11937566595754685, 'targeted_regularization': 0.11015413121290057}, 'dragonnet': {'baseline': 0.12627003463347727, 'targeted_regularization': 0.11828272347163363}, 'nednet': {'baseline': 0.12391964444731274, 'targeted_regularization': 0.1275159707153401}}
```

# Min LR

Original = 0

Test  le-5, 1e-6, 1e-7

- min_lr = 1e-5

```
The back door adjustment result is below
{'tarnet': {'baseline': 0.1215895799340942, 'targeted_regularization': 0.1356321827991395}, 'dragonnet': {'baseline': 0.11972275685923311, 'targeted_regularization': 0.12636487561929344}, 'nednet': {'baseline': 0.16572747856327386, 'targeted_regularization': 0.1799260010735252}}
the tmle estimator result is this 
{'tarnet': {'baseline': 0.11428054856066833, 'targeted_regularization': 0.11848146738253243}, 'dragonnet': {'baseline': 0.1172467026344791, 'targeted_regularization': 0.12709423358331393}, 'nednet': {'baseline': 0.12290262147288111, 'targeted_regularization': 0.1312234190115774}}
```

-  min_lr = 1e-6

```
The back door adjustment result is below
{'tarnet': {'baseline': 0.12546016347468028, 'targeted_regularization': 0.1263872835877542}, 'dragonnet': {'baseline': 0.11782778244661525, 'targeted_regularization': 0.12169198613706296}, 'nednet': {'baseline': 0.17331929386677278, 'targeted_regularization': 0.18267700910476212}}
the tmle estimator result is this 
{'tarnet': {'baseline': 0.11492120399912034, 'targeted_regularization': 0.1242505573219377}, 'dragonnet': {'baseline': 0.11670140740878843, 'targeted_regularization': 0.11261070393801091}, 'nednet': {'baseline': 0.11623494582526618, 'targeted_regularization': 0.1326805997756526}}
```

- min_lr = 1e-7

  ```
  The back door adjustment result is below
  {'tarnet': {'baseline': 0.1341776907691773, 'targeted_regularization': 0.12013399385510379}, 'dragonnet': {'baseline': 0.11704428650810034, 'targeted_regularization': 0.1634277166609177}, 'nednet': {'baseline': 0.17094127832266925, 'targeted_regularization': 0.1896334793998044}}
  the tmle estimator result is this 
  {'tarnet': {'baseline': 0.1237168631371348, 'targeted_regularization': 0.12747665740099456}, 'dragonnet': {'baseline': 0.12910178046278462, 'targeted_regularization': 0.1227766581932535}, 'nednet': {'baseline': 0.1402314021724151, 'targeted_regularization': 0.14389495392947377}}
  ```

  

#momentum

Original = 0.90

- Momentum = 0.8

```
The back door adjustment result is below
{'tarnet': {'baseline': 0.14039446346281434, 'targeted_regularization': 0.1506675011285698}, 'dragonnet': {'baseline': 0.13013085085693787, 'targeted_regularization': 0.1763532596364283}, 'nednet': {'baseline': 0.19665109235861547, 'targeted_regularization': 0.1691375842784668}}
the tmle estimator result is this 
{'tarnet': {'baseline': 0.13828491363492176, 'targeted_regularization': 0.12612324833053834}, 'dragonnet': {'baseline': 0.12679666826249728, 'targeted_regularization': 0.11626359992714395}, 'nednet': {'baseline': 0.13220083472021973, 'targeted_regularization': 0.14319595158632376}}
```

- Momentum = 0.85

```
The back door adjustment result is below
{'tarnet': {'baseline': {'back_door': 0}, 'targeted_regularization': 0}, 'dragonnet': {'baseline': 0.14484508930932313, 'targeted_regularization': 0.15054828032532494}, 'nednet': {'baseline': 0, 'targeted_regularization': 0}}
the tmle estimator result is this 
{'tarnet': {'baseline': {'back_door': 0}, 'targeted_regularization': 0}, 'dragonnet': {'baseline': 0.12949185787405773, 'targeted_regularization': 0.1195940730544058}, 'nednet': {'baseline': 0, 'targeted_regularization': 0}}
```

- Momentum = 0.95

```
The back door adjustment result is below
{'tarnet': {'baseline': {'back_door': 0}, 'targeted_regularization': 0}, 'dragonnet': {'baseline': 0.1421686322269742, 'targeted_regularization': 0.12453773796863456}, 'nednet': {'baseline': 0, 'targeted_regularization': 0}}
the tmle estimator result is this 
{'tarnet': {'baseline': {'back_door': 0}, 'targeted_regularization': 0}, 'dragonnet': {'baseline': 0.14263459147993607, 'targeted_regularization': 0.1192464772841712}, 'nednet': {'baseline': 0, 'targeted_regularization': 0}}
```


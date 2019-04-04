[1]yolodetect.py->utils.py->guess.py
[2](data.py & model.py)->train.py

1,guess.py:

```python
from model import select_model, get_checkpoint
from utils import *
```

2,
utils.py

```python
from yolodetect import PersonDetectorYOLOTiny
from yolodetect import FaceDetectorYOLO
from dlibdetect import FaceDetectorDlib
```

3,
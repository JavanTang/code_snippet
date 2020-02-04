```python
# 使用tfhub建立layer
import numpy as np
import tensorflow as tf
import tensorflow_hub as hub
embedding = "https://tfhub.dev/google/tf2-preview/gnews-swivel-20dim/1"
hub_layer = hub.KerasLayer(embedding, input_shape=[], 
                           dtype=tf.string, trainable=True)
hub_layer(train_examples_batch[:3])
```
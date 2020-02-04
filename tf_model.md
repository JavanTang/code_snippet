```python
# tf中建立模型,设置模型的优化器和loss和准确率的评判,以及训练,评估
# 建立模型
model = keras.Sequential([
    keras.layers.Flatten(input_shape=(28, 28)),
    keras.layers.Dense(128, activation='relu'),
    keras.layers.Dense(10, activation='softmax')
])
model.summary()
# 设置模型
model.compile(optimizer='adam',
              loss='sparse_categorical_crossentropy',
              metrics=['accuracy'])
# 训练模型
model.fit(train_images, train_labels, epochs=10)
# 评估模型
test_loss, test_acc = model.evaluate(test_images,  test_labels, verbose=2)
```


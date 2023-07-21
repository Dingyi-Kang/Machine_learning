SpareCategoryCrossEntropy is used when the input is integer value representing the category of the input while the CategoryCrossEntropy the input is the one-hot vectors

<img width="1466" alt="image" src="https://github.com/Dingyi-Kang/Machine_learning/assets/81428296/c3ce1047-4e8c-4fdf-8af7-23ba88d1f723">

    
    import os
    
    os.environ["TF_CPP_MIN_LOG_LEVEL"] = "2"
    
    import tensorflow as tf
    from tensorflow import keras
    from tensorflow.keras import layers
    from tensorflow.keras.datasets import mnist
    
    physical_devices = tf.config.list_physical_devices("GPU")
    tf.config.experimental.set_memory_growth(physical_devices[0], True)
    
    (x_train, y_train), (x_test, y_test) = mnist.load_data()
    x_train = x_train.reshape(-1, 28 * 28).astype("float32") / 255.0
    x_test = x_test.reshape(-1, 28 * 28).astype("float32") / 255.0
    
    # Sequential API (Very convenient, not very flexible)
    model = keras.Sequential(
        [
            keras.Input(shape=(28 * 28)),
            layers.Dense(512, activation="relu"),
            layers.Dense(256, activation="relu"),
            layers.Dense(10),
        ]
    )
    
    model = keras.Sequential()
    model.add(keras.Input(shape=(784)))
    model.add(layers.Dense(512, activation="relu"))
    model.add(layers.Dense(256, activation="relu", name="my_layer"))
    model.add(layers.Dense(10))
    
    # Functional API (A bit more flexible)
    inputs = keras.Input(shape=(784))
    x = layers.Dense(512, activation="relu", name="first_layer")(inputs)
    x = layers.Dense(256, activation="relu", name="second_layer")(x)
    outputs = layers.Dense(10, activation="softmax")(x)
    model = keras.Model(inputs=inputs, outputs=outputs)
    
    model.compile(
        loss=keras.losses.SparseCategoricalCrossentropy(from_logits=False),
        optimizer=keras.optimizers.Adam(lr=0.001),
        metrics=["accuracy"],
    )
    
    model.fit(x_train, y_train, batch_size=32, epochs=5, verbose=2)
    model.evaluate(x_test, y_test, batch_size=32, verbose=2)

## you can also get the output(s) from the certain layer(s) in the middle
<img width="1183" alt="image" src="https://github.com/Dingyi-Kang/Machine_learning/assets/81428296/5ca487fb-08f4-4875-a3e8-ab5c5538138c">
<img width="300" alt="image" src="https://github.com/Dingyi-Kang/Machine_learning/assets/81428296/3db1bd79-ced9-4777-a28a-f204f0d95c76">
<img width="1433" alt="image" src="https://github.com/Dingyi-Kang/Machine_learning/assets/81428296/e9d62488-1292-427b-982f-4530d7a3ea0c">
<img width="1471" alt="image" src="https://github.com/Dingyi-Kang/Machine_learning/assets/81428296/0279ad57-9a1a-49df-a13b-5f66e1a5518d">
<img width="264" alt="image" src="https://github.com/Dingyi-Kang/Machine_learning/assets/81428296/afdbce33-6900-445b-949a-1de2231b511b">




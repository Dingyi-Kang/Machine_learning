# Note: the tutorial created a class of keras.layers.layer and a class of kera.Model --- this is inherentance in Python
## For instance, keras.Model has built-in functions of evaluate, evaluate, and predict, etc. it also has built-in properties like layers, summary

    import os
    
    os.environ["TF_CPP_MIN_LOG_LEVEL"] = "2"
    import tensorflow as tf
    from tensorflow import keras
    from tensorflow.keras import layers
    from tensorflow.keras.datasets import mnist
    
    physical_devices = tf.config.list_physical_devices("GPU")
    tf.config.experimental.set_memory_growth(physical_devices[0], True)
    
    (x_train, y_train), (x_test, y_test) = mnist.load_data()
    x_train = x_train.reshape(-1, 28, 28, 1).astype("float32") / 255.0
    x_test = x_test.reshape(-1, 28, 28, 1).astype("float32") / 255.0
    
    # CNN -> BatchNorm -> ReLU (common structure)
    # x10 (a lot of code to write!)
    
    
    class CNNBlock(layers.Layer):
        def __init__(self, out_channels, kernel_size=3):
        #init super class first
            super(CNNBlock, self).__init__()
            self.conv = layers.Conv2D(out_channels, kernel_size, padding="same")
            self.bn = layers.BatchNormalization()
        # this call function is equivalent to the forward function in pytorch
        def call(self, input_tensor, training=False):
            x = self.conv(input_tensor)
            x = self.bn(x, training=training)
            x = tf.nn.relu(x)
            return x
    
    
    model = keras.Sequential(
        [CNNBlock(32), CNNBlock(64), CNNBlock(128), layers.Flatten(), layers.Dense(10),]
    )
    
    
    class ResBlock(layers.Layer):
        def __init__(self, channels):
            super(ResBlock, self).__init__()
            self.channels = channels
            self.cnn1 = CNNBlock(channels[0], 3)
            self.cnn2 = CNNBlock(channels[1], 3)
            self.cnn3 = CNNBlock(channels[2], 3)
            self.pooling = layers.MaxPooling2D()
            # because this is identity so the kernel is 1, in other words, this is a shortcut and we just want to change the dimension of channels
            self.identity_mapping = layers.Conv2D(channels[1], 1, padding="same")
    
        def call(self, input_tensor, training=False):
            x = self.cnn1(input_tensor, training=training)
            x = self.cnn2(x, training=training)
            x = self.cnn3(x + self.identity_mapping(input_tensor), training=training,)
            x = self.pooling(x)
            return x
    
    
    class ResNet_Like(keras.Model):
        def __init__(self, num_classes=10):
            super(ResNet_Like, self).__init__()
            self.block1 = ResBlock([32, 32, 64])
            self.block2 = ResBlock([128, 128, 256])
            self.block3 = ResBlock([128, 256, 512])
            #This average matrix of a feature dimension, namely condense heigh and width into one and reduce the dimension --- alternative way of using Flatten
            self.pool = layers.GlobalAveragePooling2D()
            self.classifier = layers.Dense(num_classes)
        # this call function is equivalent to the forward function in pytorch
        # the passed on training will be specified in the model.fit, model.evaluate corresondingly
        def call(self, input_tensor, training=False):
            x = self.block1(input_tensor, training=training)
            x = self.block2(x, training=training)
            x = self.block3(x, training=training)
            x = self.pool(x, training=training)
            x = self.classifier(x)
            return x
        # this overwrite the call function so that the shape can be printed out in the model.Summary
        def model(self):
            x = keras.Input(shape=(28, 28, 1))
            return keras.Model(inputs=[x], outputs=self.call(x))
    
    
    model = ResNet_Like().model()
    base_input = model.layers[0].input
    base_output = model.layers[2].output
    output = layers.Dense(10)(layers.Flatten()(base_output))
    model = keras.Model(base_input, output)
    
    model.compile(
        optimizer=keras.optimizers.Adam(),
        loss=keras.losses.SparseCategoricalCrossentropy(from_logits=True),
        metrics=["accuracy"],
    )
    # when model.fit is called, the train=True will be automatically passed to the custom class of blocks of layers
    model.fit(x_train, y_train, batch_size=64, epochs=1, verbose=2)
    # when model.fit is called, the train=False will be automatically passed to the custom class of blocks of layers
    model.evaluate(x_test, y_test, batch_size=64, verbose=2)
    model.save("pretrained")


<img width="2240" alt="image" src="https://github.com/Dingyi-Kang/Machine_learning/assets/81428296/dc138752-f77a-497b-b33e-561bf6b30ff6">

# To walk around this issue, overwrite the call function so that the shape can be printed out in the model.Summary
        def model(self):
            x = keras.Input(shape=(28, 28, 1))
            return keras.Model(inputs=[x], outputs=self.call(x))
        # then call
        print(model.model().summary())
        
<img width="1449" alt="image" src="https://github.com/Dingyi-Kang/Machine_learning/assets/81428296/7e45711d-c8a3-48e0-b978-db9d4cecd630">
<img width="1381" alt="image" src="https://github.com/Dingyi-Kang/Machine_learning/assets/81428296/5a49b0fd-1089-47a0-983f-2be4325dd78e">


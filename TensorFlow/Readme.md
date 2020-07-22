
# Artificial Neural Network(ANN) Learning Model using TensorFlow


The POC, illustrates training the datasets from MNIST containing handwritten digits and plotting the accuracy per iteration. The following are the steps to train the data sets and to find the accuracy of the leaning model.


**Steps for Artificial Neural Network Model to train the dataset and to find the accuracy of the model using TensorFlow:**

1.	Install TensorFlow in Google Colaboratory(colab) Notebook.

        !pip install -q tensorflow==2.0.0-beta1

2.	Load the MNIST datasets using **keras.datasets.mnist** as shown below.

       	# Load the Data
        import tensorflow as tf
        mnist = tf.keras.datasets.mnist
        (x_train, y_train), (x_test, y_test) = mnist.load_data()
        x_train, x_test = x_train / 255.0, x_test / 255.0
        print("x_train.shape:", x_train.shape)
       
	![Alt text](https://github.com/Protontech-1803/Machine_Learning/blob/master/TensorFlow/TensorFlow_PNG/LoadData.png)
 
3.	Build and compile the model using functional API’s as shown below.

        # Build the Model
        model = tf.keras.models.Sequential([
          tf.keras.layers.Flatten(input_shape=(28, 28)),
          tf.keras.layers.Dense(128, activation='relu'),
          tf.keras.layers.Dropout(0.2),
          tf.keras.layers.Dense(10, activation='softmax')
        ])

        # Compile the Model
        model.compile(optimizer='adam',
              loss='sparse_categorical_crossentropy',
              metrics=['accuracy'])
	      
	![Alt text](https://github.com/Protontech-1803/Machine_Learning/blob/master/TensorFlow/TensorFlow_PNG/Build_Compile_Model.png)
 
4.	Once the model is created and complied, train the model using **model.fit** as shown below.

         # Train the model
         r = model.fit(x_train, y_train, validation_data=(x_test, y_test), epochs=10)
       
	![Alt text](https://github.com/Protontech-1803/Machine_Learning/blob/master/TensorFlow/TensorFlow_PNG/Train_Model.png)
 
5.	Plot the graph using **matplotlib** library as shown below
	**Note:** Blue line - Training set data
	Red line – Testing set data for the machine
	
         # Plot accuracy per iteration
         import matplotlib.pyplot as plt
         plt.plot(r.history['accuracy'], label='acc')
         plt.plot(r.history['val_accuracy'], label='val_acc')
         plt.legend()
       
	![Alt text](https://github.com/Protontech-1803/Machine_Learning/blob/master/TensorFlow/TensorFlow_PNG/Accuracy_Graph.png)

 
6.	Evaluate the models accuracy using **model.evaluate** API.

        # Evaluate the model
        print(model.evaluate(x_test, y_test))

	![Alt text](https://github.com/Protontech-1803/Machine_Learning/blob/master/TensorFlow/TensorFlow_PNG/Evaluate_Model.png)
 
7.	The model is 98% accurate as shown above snapshot.





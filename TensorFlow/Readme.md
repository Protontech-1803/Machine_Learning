
# ANN Learning Model using TensorFlow

The POC, illustrates training the datasets from MNIST containing handwritten digits and plotting the accuracy per iteration. The following are the steps to train the data sets and to find the accuracy of the leaning model.

**Steps for Artificial Neural Network Model to train the dataset and to find the accuracy of the model using TensorFlow:**

1.	Install TensorFlow in Google Colaboratory(colab) Notebook.

        !pip install -q tensorflow==2.0.0-beta1

2.	Load the MNIST datasets using **keras.datasets.mnist** as shown below.

	![Alt text](https://github.com/Protontech-1803/Machine_Learning/blob/master/TensorFlow/TensorFlow_PNG/LoadData.png)
 
3.	Build and compile the model using functional API’s as shown below.

	![Alt text](https://github.com/Protontech-1803/Machine_Learning/blob/master/TensorFlow/TensorFlow_PNG/Build_Compile_Model.png)
 
4.	Once the model is created and complied, train the model using **model.fit** as shown below.

	![Alt text](https://github.com/Protontech-1803/Machine_Learning/blob/master/TensorFlow/TensorFlow_PNG/Train_Model.png)
 
5.	Plot the graph using **matplotlib** library as shown below
	**Note:** Blue line - Training set data
	Red line – Testing set data for the machine
	
	![Alt text](https://github.com/Protontech-1803/Machine_Learning/blob/master/TensorFlow/TensorFlow_PNG/Accuracy_Graph.png)

 
6.	Evaluate the models accuracy using **model.evaluate** API.

	![Alt text](https://github.com/Protontech-1803/Machine_Learning/blob/master/TensorFlow/TensorFlow_PNG/Evaluate_Model.png)
 
7.	The model is 98% accurate as shown above snapshot.





This demonstration walks you through the full lifecycle of a custom object detection task — from data preparation to model deployment. All tasks are performed in a Google Colab notebook for ease of use and accessibility.

⸻

Key Stages of the Project

1. Data Preparation
	•	Annotate your images using a tool like LabelImg to draw bounding boxes and save the .xml files.
	•	Convert these annotated images into the .tfrecord format, which is required for training using the TensorFlow Object Detection API.

2. Model Configuration
	•	Select a pre-trained object detection model from the TensorFlow Model Zoo.
	•	Modify the model’s configuration file to reference your custom dataset, label map, training parameters, and TFRecord paths.

3. Training
	•	Use the provided Colab notebook to install dependencies and start training the model using a free GPU.
	•	You can monitor performance metrics like loss as the model trains.

4. Export and Inference
	•	Once the model is trained, export it as a frozen inference graph.
	•	Use the exported model to make predictions on new images.

How to Use This Repository

1. Preparing Your Data
	•	Place your images in:
./data/images/train/
./data/images/test/

	•	Save the .xml annotation files from LabelImg in the same folders as the images.
	•	If using a forked GitHub repo, commit and push these images and annotation files.

2. Training the Model
	•	Open the notebook tensorflow_object_detection_training_colab.ipynb.
	•	Set the repo_url variable to point to your GitHub repository.
	•	Run the notebook cells sequentially to set up the environment, create TFRecords, and train the model.

3. Inference
	•	Use local_inference_test.ipynb to test your trained model on local images.
	•	For performance-optimized deployment on Intel devices, follow the guide to use the OpenVINO toolkit.

⸻

Requirements
	•	Frozen Inference Graph
File: frozen_inference_graph.pb
This is your trained model, downloadable after training in Colab.
	•	Label Map
File: label_map.pbtxt
Maps model output indices to class names. Also generated in the notebook.

⸻

Configs and Hyperparameters

This project supports a wide variety of object detection models. You can find more pretrained models in the TensorFlow Detection Model Zoo, as well as their pipeline configuration files in object_detection/samples/configs/.

⸻
**
Built by Siddarth Valasubramanian**

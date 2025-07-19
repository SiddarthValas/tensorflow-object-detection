⸻

Object Detection with TensorFlow

This project provides a complete walkthrough for building a custom object detection model using the TensorFlow Object Detection API. The entire process is designed to run in a Google Colab notebook, making it accessible without the need for local setup.

⸻

Key Stages of the Project

Data Preparation
	•	Annotate images using LabelImg to draw bounding boxes.
	•	Save the annotations as .xml files.
	•	Convert the .xml files into the .tfrecord format required by TensorFlow.

Model Configuration
	•	Choose a pre-trained object detection model from the TensorFlow Model Zoo.
	•	Modify the selected model’s pipeline configuration file to:
	•	Reference your custom dataset
	•	Define training and evaluation parameters
	•	Point to your label map and TFRecord paths

Training
	•	Use the provided Colab notebook to:
	•	Install all necessary dependencies
	•	Prepare your dataset
	•	Train the model using a free GPU
	•	Monitor training performance via metrics like loss

Export and Inference
	•	Once training is complete, export the model as a frozen inference graph.
	•	Use this trained model to make predictions on new, unseen images.

⸻

How to Use This Repository

1. Preparing Your Data
	•	Organize your images into the following structure:

./data/images/train/
./data/images/test/


	•	Store the .xml annotation files from LabelImg in the same directories.
	•	If working from a forked repository, commit and push the image and annotation files.

2. Training the Model
	•	Open the notebook tensorflow_object_detection_training_colab.ipynb.
	•	Set the repo_url variable to point to your GitHub repository.
	•	Run the notebook cells sequentially to:
	•	Install dependencies
	•	Create TFRecords
	•	Start the training process

3. Inference
	•	Use local_inference_test.ipynb to run inference on new images.
	•	For optimized deployment on Intel devices, refer to the provided OpenVINO integration guide.

⸻

Requirements
	•	Frozen Inference Graph (frozen_inference_graph.pb)
This is the exported, trained model, downloadable after training in Colab.
	•	Label Map File (label_map.pbtxt)
Maps model output class indices to readable class names. Generated and downloaded in the notebook.

⸻

Configs and Hyperparameters

This project supports a wide range of object detection models. You can explore additional pre-trained models and their configuration files in the TensorFlow Detection Model Zoo and under object_detection/samples/configs/.

⸻

Built by Siddarth Valasubramanian

⸻

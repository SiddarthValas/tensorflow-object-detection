

⸻

Custom Object Detection with TensorFlow

This repository provides a complete pipeline for training your own custom object detection model using the TensorFlow Object Detection API. The process is simplified using Google Colab, making it easy to run on free GPU hardware without any local setup.

⸻

Overview

This project demonstrates the full lifecycle of a custom object detection task — from dataset preparation to training, exporting, and performing inference on new images. All major steps are integrated into a Colab notebook.

⸻

Key Stages of the Project

1. Data Preparation
	•	Annotate your images using a tool like LabelImg.
	•	Save the .xml annotation files in the same folders as the corresponding images.
	•	Convert the annotated data into TFRecord format — a TensorFlow-compatible format for training.

2. Model Configuration
	•	Choose a pre-trained model from the TensorFlow Model Zoo.
	•	Edit the model’s pipeline.config to:
	•	Set the paths for TFRecord files
	•	Link your label_map.pbtxt
	•	Adjust training parameters (e.g., batch size, learning rate)

3. Model Training
	•	Use the tensorflow_object_detection_training_colab.ipynb notebook.
	•	It installs dependencies, sets up the environment, and initiates training.
	•	Training can be monitored in real time (e.g., loss values, step count).

4. Model Export and Inference
	•	After training, export the model as a frozen inference graph.
	•	Run inference on new images using the local_inference_test.ipynb notebook.
	•	For optimized performance (especially on Intel devices), deployment via OpenVINO is also supported.

⸻

Repository Usage

Preparing Your Data
	1.	Organize your dataset:

./data/images/train/
./data/images/test/


	2.	Save annotated .xml files in the same folders as images.
	3.	If using a forked repo, push all image and annotation files to your fork.

Training the Model
	1.	Open tensorflow_object_detection_training_colab.ipynb.
	2.	Set the repo_url variable to your GitHub repository.
	3.	Run the notebook cells sequentially to:
	•	Install required packages
	•	Convert data to TFRecord
	•	Start training the model

Running Inference
	•	Use local_inference_test.ipynb for testing the model locally on new images.
	•	Optionally, follow the OpenVINO guide in the repo for optimized deployment.

⸻

Requirements
	•	Frozen Inference Graph (frozen_inference_graph.pb)
Exported after training, this is the actual model used for inference.
	•	Label Map File (label_map.pbtxt)
Maps class indices (e.g., 0, 1, 2) to human-readable class names. Also generated in the notebook.

⸻

Configs and Hyperparameters

This project supports a wide variety of object detection models. You can explore additional pre-trained models and configuration files at:

TensorFlow Detection Model Zoo
Config files: object_detection/samples/configs/

You may modify these configs to tune the learning rate, optimizer type, augmentation, evaluation metrics, etc.

⸻

Built by Siddarth Valasubramanian

⸻

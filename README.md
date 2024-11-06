# AIwithAzure
# Azure AI Labs: Language Detection and Image Analysis

This repository contains three labs that utilize Azure's Cognitive Services APIs to perform tasks such as language detection, image analysis, and text extraction. The labs demonstrate both REST API and SDK client implementations to interact with Azure's Text Analytics and Computer Vision services.

## Prerequisites

Before you begin, ensure you have the following:

- **Azure Subscription**: An Azure account with access to Cognitive Services.
- **API Key and Endpoint**: Set up a Cognitive Services resource in Azure and obtain your API key and endpoint.

### Required Libraries

Install the required Python packages by running the following commands:

pip install python-dotenv
pip install azure-ai-textanalytics
pip install azure-ai-vision
pip install azure-core
pip install requests
pip install matplotlib
pip install pillow

Environment Setup
Clone this repository and navigate to the project directory.
Create a .env file in the project root and add your Azure API endpoint and key as follows (replace with your actual values):
plaintext

AI_SERVICE_ENDPOINT="https://your-azure-endpoint.cognitiveservices.azure.com/"
AI_SERVICE_KEY="your-api-key"

Lab 1: Language Detection
In Lab 1, you'll implement a language detection tool that uses Azure's Text Analytics API to identify the language of a given text input.

Instructions
You can choose between two methods for implementing language detection:

REST API Client
To run the language detection using the REST API client, execute the following command:


python lab1_rest_client.py
This script will prompt you to enter text, and it will detect the language using the REST API method until you type quit.

SDK Client
To run the language detection using the Azure SDK client, execute:

python lab1_sdk_client.py

This script will also prompt you to enter text and detect the language using the Azure SDK.

Features
Detects the language of text input.
Supports continuous input until "quit" is entered.
Provides the language name based on the Text Analytics API results.


Lab 2: Image Analysis and Background Removal
In Lab 2, you'll analyze images to extract captions, tags, objects, and people using Azure's Computer Vision API. Additionally, this lab includes a feature to remove the image background.

Instructions
To run the image analysis and background removal using the SDK client, execute:

python lab2_image_analysis.py [image_path]

By default, this script analyzes the image located at images/street.jpg, but you can specify a different image path as an argument.

Output Files
The analysis results will be saved as annotated images, including detected objects, people, and a version with the background removed:

objects.jpg: Annotated image showing detected objects.
people.jpg: Annotated image showing detected people.
background.png: Image with background removed.

Features
Caption Generation: Describes the content of the image.
Tags Extraction: Lists tags based on the image content.
Object and People Detection: Detects objects and people in the image, drawing bounding boxes.
Background Removal: Removes the background or generates a foreground matte for the image.


Lab 3: Text Extraction and Analysis Using Azure AI Vision
In Lab 3, you'll use Azure's AI Vision services to read and analyze text from images. This lab demonstrates how to extract text and overlay detected text with bounding polygons on the original image.

Prerequisites
Azure API Key and Endpoint: You'll need the Azure API endpoint and key for the Image Analysis service.

Setup
Clone or download the repository.
Install the dependencies by running:

pip install -r requirements.txt

Set up the environment variables by creating a .env file in the root directory and adding your Azure API endpoint and key:

AI_SERVICE_ENDPOINT=your_endpoint_here
AI_SERVICE_KEY=your_key_here

Place the images you want to analyze (e.g., Lincoln.jpg, Note.jpg) inside an images folder in the project directory.
Usage
Run the script by executing:

python lab-03.py

You will then be prompted to select an option from the following menu:

Use the Read API to extract text from Lincoln.jpg.
Extract handwriting from Note.jpg.
Press any other key to exit.
Output
The extracted text will be displayed in the console.
The original image will be annotated with bounding polygons around the detected text.
The annotated image will be saved as text.jpg in the project directory.

Features
Extracts printed and handwritten text from images.
Displays confidence scores for the detected text.
Overlays bounding polygons around detected text.

Troubleshooting
.env File Configuration: Ensure that the .env file is properly configured with your Azure API endpoint and key.
Required Python Packages: Verify that all required Python packages are installed by running pip install -r requirements.txt or manually installing them.
Image Path Issues: Ensure that the image paths you provide for analysis are correct and accessible.
API Key or Endpoint Issues: If you encounter authentication issues, verify that your Azure API key and endpoint are correctly set up.

# ChromaDB Plugin for LM Studio

The ChromaDB Plugin for [LM Studio](https://lmstudio.ai/) adds a vector database to LM Studio utilizing ChromaDB! Tested on a 1000 page legal treatise.

## Table of Contents
1. [Installation Instructions](#installation-instructions)
2. [Usage Guide](#usage-guide)
3. [Important Notes](#important-notes)
4. [Feedback](#feedback)
5. [Final Notes](#final-notes)

## Installation Instructions
* **Step 1**: Download all the files in this repository and put them into a directory.
* **Step 2**: Install [CUDA 11.8](https://developer.nvidia.com/cuda-11-8-0-download-archive) if it's not already installed.
* **Step 3**: Go to the folder where my repository is located, open a command prompt and run: `python -m venv .`
* **Step 4**: Then run: `.\Scripts\activate`
* **Step 5**: Then run: `pip install -r requirements.txt`
* **Step 6**: Then run: `pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118`

## Usage Guide
* **Step 1**: In the same command prompt, run: `python gui.py`
* **Step 2**: Click the "Choose Documents" button and choose one or more documents to include in the vector database.
  * **Note**: Only PDFs with OCR done on them will work as of Version 1. A folder named "Docs_to_DB" will be created and populated.
* **Step 3**: Click the "Create ChromaDB" button. A folder named "Vector_DB" will be created if it doesn't already exist.
  * **Note**: A message will appear with instructions on how to monitor CUDA usage. Please follow them.
  * **Note**: The embedding model will be downloaded to your cache folder if it's not downloaded already. Once downloaded, the vector database will automatically be created. Watch your CUDA usage to verify that it's working - pretty awesome! The database is created when CUDA usage drops to zero.
* **Step 4**: Open LM Studio, select a model, and click "Start Server."
  * **Note**: The formatting of the prompt in my scripts is specifically geared to work with any Llama2 "chat" models. Any others likely won't work as well or even return an intelligible response. This will be addressed in future versions.
  * **Note**: If you don't start the server before entering your query and clicking "Submit Query," it will give an error.
* **Step 5**: Enter your query and click the "Submit Query" button and be amazed at the response you get.
  * **Note**: For extra fun, have the LM Studio window visible to see its log, which shows interactions with the vector database!

## Important Notes
* **Compatibility**: This is a personal project and was specifically tested using CUDA 11.8 and the related PyTorch installation.
* **Embedding Model**: This plugin uses "hkunlp/instructor-large" as the embedding model. Look [here](https://huggingface.co/spaces/mteb/leaderboard) for more details. If people express an interest, I'll likely include other embedding models in future versions!

## Feedback
My motivation to improve this beyond what I personally use it for is directly related to people's interest and suggestions. All feedback, positive and negative, is welcome! I can be reached at the LM Studio discord server or "bbc@chintellalaw.com".

## Final Notes
* **Note**: I only tested this on Windows 10 but can possibly expand on this in later versions.
* **Note**: Please be aware that when you click "Create Database" as well as "Submit Query" the GUI will hang. Just wait...it'll resume. This is a minor characteristic of the scripts that can easily be fixed in future versions.
* **Note**: Everytime you want to use the program again, enter the folder, activate the virtual enviroment using `.\Scripts\activate` and run `python gui.py`.

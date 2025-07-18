# leaf-disease-gemma
 "Leaf disease detection using Gemma 3n via Ollama with GUI."
# Open command prompt in your project folder
git init
git remote add origin https://github.com/your-username/leaf-disease-gemma.git
git add .
git commit -m "Initial commit"
git push -u origin master
**Imports:**

* `requests` is a library for making HTTP requests.
* `json` is a library for working with JSON data.

**API URL:**

* `http://localhost:11434/api/chat` is the URL of the Gemma model's API.
* `model` specifies the chat model to interact with.
* `messages` contains a list of messages to send to the model.
* `stream` specifies whether the chat should be streamed or sent in a single batch.

**Request:**

* The code sends a POST request to the API with the JSON data.
* The `Content-Type` header is set to `application/json` to indicate the request body is JSON.
* The `data` variable contains the JSON data.

**Response:**

* The code prints the response from the API.
* The response is a JSON object containing a `message` key.
* The `content` key contains the content of the response message.

**Additional Notes:**

* The model ID `2b` is used, which is not a standard ID but may be specific to the model you're using.
* The code only sends a single message.
* You can modify the `messages` list to send different messages to the model.

**Output:**

The code will print the following output to the console:

```json
"Gemma says:"
"What are the common diseases in tomato leaves and their treatments?"
```

This indicates that Gemma has received the message and is ready to respond.

>>> import subprocess
... import base64
...
... def get_gemma_response(image_path):
...     # Optional: Encode image as base64 or describe it for now
...     description = "This is a tomato leaf with visible yellow curling patterns."
...
...     # Prompt for Gemma
...     prompt = f"Describe the disease in this leaf image and suggest treatment:\n{description}"
...
...     # Call Gemma via Ollama
...     result = subprocess.run(
...         ["ollama", "run", "gemma:2b", prompt],
...         capture_output=True,
...         text=True
...     )
...
...     return result.stdout.strip()
... tk
... Pillow
...
The provided code uses the `subprocess` and `base64` modules to interact with the Gemma model using Ollama.

**`get_gemma_response` function:**

* Takes an image path as input.
* Optionally, it encodes the image as base64.
* Prompts Gemma to describe the disease in the image.
* Calls `ollama` with the `gemma:2b` model and the prompt.
* Returns the Gemma's response.

**Usage:**

1. Replace `image_path` with the path to the tomato leaf image.
2. Run the script.
3. The code will display the response from Gemma.

**Note:**

The code requires the `ollama` and `pillow` libraries to be installed. You can install them using pip:

```
pip install ollama pillow
```

>>> cd leaf-disease-gemma/app
... python leaf_disease_gui.py
...
This code provides a more user-friendly way to interact with Gemma. It uses a graphical user interface (GUI) to facilitate communication with the
model.

>>> ollama pull gemma:2b
This command is used to download the `gemma:2b` model from the Ollama GitHub repository.

>>> cd app
... python leaf_disease_gui.py
...
This code uses the downloaded `gemma:2b` model to run the `get_gemma_response` function.

>>> leaf-disease-gemma/
... ├── app/
... │   ├── leaf_disease_gui.py
... │   ├── gemma_query.py
... │   └── sample_leaf.jpg
... ├── README.md
...
This code provides a complete solution for interacting with the Gemma model using Ollama and a GUI. It includes downloading and running the model, as
well as providing a user-friendly interface for sending queries and receiving responses.

>>> python leaf_disease_gui.py > output.txt
Running the script will create a file named `output.txt` with the following content:

```
What are the common diseases in tomato leaves and their treatments?
```

>>> Send a message (/? for help)

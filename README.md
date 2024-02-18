# Sintetica - ⓍXTTS🎙️

Welcome to the ⓍXTTS fine tuning repository! 👋

[ⓍTTS](https://docs.coqui.ai/en/latest/models/xtts.html) is a super cool Text-to-Speech model that lets you clone voices in different languages by using just a quick 3-second audio clip. Built on the 🐢Tortoise, ⓍTTS has important model changes that make cross-language voice cloning and multi-lingual speech generation super easy. There is no need for an excessive amount of training data that spans countless hours.

[Hugging Face](https://huggingface.co/coqui/XTTS-v2)

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/mecantronic/sintetica-service-xtts/blob/main/notebooks/xtts_finetuning.ipynb)

## Installation 🛠️
1. Clone the repository:
```bash
    git clone --branch main -q  https://github.com/mecantronic/sintetica-service-xtts.git
```
2. Navigate to the project directory:
```bash
    cd sintetica-service-xtts
```
3. Create a virtual environment:
```bash
    python3 -m venv env
```
4. Activate the virtual environment:
```bash
    source env/bin/activate
```
5. Install the required dependencies:
```bash
    pip install --use-deprecated=legacy-resolver -q -e TTS
    pip install --use-deprecated=legacy-resolver -q -r TTS/TTS/demos/xtts_ft_demo/requirements.txt
    pip install -q typing_extensions==4.8 numpy==1.26.2
```

## Getting Started 🚀
Follow these steps to unleash the power of ⓍXTTS:

1. Data Processing 🎧
* Upload audio files for training.
* Specify the output path and select the dataset language.
* Click "Step 1 - Create dataset" to process the data.

2. Fine-Tuning ⓍXTTS Encoder 🚄
* Set the paths for training and evaluation CSV files.
* Adjust hyperparameters like epochs, batch size, and more.
* Click "Step 2 - Run the training" to fine-tune the ⓍXTTS model.

3. Inference 🧠
* Load the fine-tuned ⓍXTTS model by providing checkpoint, config, and vocab paths.
* Specify a speaker reference audio for inference.
* Choose the language and input text for speech synthesis.
* Click "Step 3 - Load Fine-tuned ⓍXTTS model" and then "Step 4 - Inference."

## Gradio Demo 🌐
Access the live Gradio demo here after running the provided commands.

```bash
    python3 TTS/TTS/demos/xtts_ft_demo/xtts_finetunning.py --batch_size 2 --num_epochs 6
```

## Command Line Arguments 🛠️
You can customize the behavior of the XTTS Fine-Tuning Demo using the following command line arguments:

* --port: Port to run the Gradio demo. Default: 5003.
* --out_path: Output path (where data and checkpoints will be saved). Default: /tmp/xtts_ft/.
* --num_epochs: Number of epochs to train. Default: 10.
* --batch_size: Batch size. Default: 4.
* --grad_acumm: Gradient accumulation steps. Default: 1.
* --max_audio_length: Maximum permitted audio size in seconds. Default: 11.

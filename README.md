# APAI26-LAB03: DNN Shrinking and Quantization

## Material

- Slides: [here](./_docs/slides.pdf)
- Notebook (assignment): [here](./APAI26-LAB3-DNN-Shrinking-and-Quantization.ipynb)
- Pre-trained weights of the Lab 02 CNN: [ExampleNet.pth](./ExampleNet.pth) (the notebook downloads them automatically)

## Summary

In this lab we will take the CNN from Lab 02 and make it smaller and integer-only. The slides introduce DNN shrinking techniques (fewer channels, fewer layers, larger stride) and quantization (post-training quantization, quantization-aware training, true quantization); the notebook then guides you through applying them to the network trained on the [Fashion-MNIST](https://github.com/zalandoresearch/fashion-mnist) dataset.

The assignment is contained entirely in the notebook. Each task comes with its own resources, sub-tasks and tips:

0. Set up the environment
1. Load the pre-trained model
2. Reduce the network's size under 5M MAC (halve the number of channels)
3. Retrain the reduced network and verify its accuracy
4. Quantize the reduced network: quantize a tensor by hand, fake-quantize the network with [Brevitas](https://github.com/Xilinx/brevitas) (PTQ and QAT), then true-quantize it with DeepQuant
5. Export the float32 and true-quantized models to ONNX and analyze them with [Netron](https://netron.app)

Guidelines to work on today's assignment:

1. Read the [slides](./_docs/slides.pdf)
2. Set up the environment, preferably on Google Colab, or locally in VS Code (see [Quickstart](#quickstart))
3. Complete Tasks 0-5 in the [Jupyter notebook](./APAI26-LAB3-DNN-Shrinking-and-Quantization.ipynb)

**AI policy:** we will not prevent you from using AI to solve the assignments, but the lab is meant to be a hands-on learning experience. To keep it useful, this repository includes an [AGENTS.md](./AGENTS.md) file (also used in a Stanford class) that AI agents should read automatically, so that they guide you towards finding the solution yourself instead of giving it to you directly.

## How to deliver the assignment

1. Run all the cells and save the notebook, so that the results show up in the cells. Do **NOT** clear the outputs of the cells.
2. Rename the notebook to `LAB3_APAI_<name_surname>.ipynb`
3. Upload it to Virtuale:
    - If you run on Colab, download it first (`File → Download → Download .ipynb`), then upload it
    - If you run locally, upload the saved notebook directly from your PC

For each lab that you solve and submit successfully, you will receive 1 extra point, up to a maximum of 4 points.

**Assignment DEADLINE: Sunday, 01/11/2026 (at 23:59)**

___

## Quickstart

**This lab must be run on your own personal computer**, since the lab machines have very limited internet access, which doesn't allow you to access Google Colab or to download the necessary libraries.

There are 2 ways to complete the assignment. We recommend Google Colab:

### Option 1 (preferred): Running on Google Colab

[Google Colab](https://colab.research.google.com/) runs Python notebooks in the cloud and is accessed via your browser, so it should work on any system.

1. Download the notebook, either from Virtuale or by cloning this repository
2. Open Google Colab and choose the "Upload notebook" ("Carica notebook") option
3. Use the pop-up to upload the notebook that you just downloaded
4. Use a CPU runtime (`Runtime → Change runtime type → CPU`): the lab does not need a GPU
5. Run the setup cell (Task 0) **once**: it installs the required packages and restarts the runtime automatically
6. Now you're ready to start!

### Option 2: Running locally, in VS Code

1. Clone this repository:
```
git clone https://github.com/EEESlab/APAI26-LAB03-DNN-Shrinking-and-Quantization
cd APAI26-LAB03-DNN-Shrinking-and-Quantization/
```
2. Open the notebook in VS Code. It should work with minimal setup: if any component is missing (e.g., the Python or Jupyter extensions, or the kernel), VS Code will direct you to install it.
3. Run the setup cell (Task 0) **once**, preferably in a dedicated virtual environment, since it installs specific versions of PyTorch and other packages.
4. Now you're ready to start! The cells that download files with `google.colab` only work on Colab: locally, you can open the ONNX files directly from the working directory.

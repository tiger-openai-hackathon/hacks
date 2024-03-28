# Tiger Analytics - Azure OpenAI Hackathon

Welcome to the Azure OpenAI hackathon organized by Microsoft in partnership with Tiger Analytics. This repository contains information (data, instructions for the workshop, and reference material) related to **Setting RAG solutioning using Azure AI services** conducted by Microsoft and Tiger Analytics.

1. The sample data that will be used during the session is available in the [data](data) folder
2. The presentation that will be used during the session is available in the [references](references/TA_presentation.pdf) folder
3. Detailed instructions to follow during the session are available in the [instructions](instructions/ms_hack_steps_ai_studio.pdf) folder
4. Additional references can be found in the [references](references) folder. It also contains some sample prompts and questions that can be asked on the dataset.

Please feel free to reach out to the trainers during the session, for any questions or issues related to access or the
solution. We hope you have a rewarding experience during the hack event.

## Prerequisites

### Azure Account

An Azure account is necessary for resources provided in the code. You can use your organization's Azure account if available. If not create one from here: <https://azure.microsoft.com/en-us/free/>

### Operating System

Windows and Linux are the preferred operating systems for the hack event. They're preferred as the tools and libraries are tested in Windows and Linux. Macbooks can be used if there are no alternatives, but challenges are to be expected.

### Python Environment

Python version **3.9** needs to be installed on the local machine used for the hack. Refer to the instructions below to install Miniconda and create a Python 3.9 environment.

1. Install Miniconda following the documentation (skip this step if you already have Anaconda or Miniconda installed): [https://docs.anaconda.com/free/miniconda/#quick-command-line-install](https://docs.anaconda.com/free/miniconda/#quick-command-line-install). If you have Anaconda or Miniconda already installed in your system, you can skip this step.
2. [Clone](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository) or [download](https://docs.github.com/en/repositories/working-with-files/using-files/downloading-source-code-archives#downloading-source-code-archives-from-the-repository-view) the [main branch](https://github.com/tiger-openai-hackathon/hacks) of this repository in your local system
3. For Windows users, it is preferred to add `conda` as a `PATH` variable. Open a new terminal and try entering the command: `conda`. If you get a message saying "Conda command not recognized", then please add `conda` to `PATH` manually by following the steps in this [link](https://saturncloud.io/blog/solving-the-conda-command-not-recognized-issue-on-windows-10/). This is an optional step and can be skipped if you want to use the Anaconda prompt instead of the command prompt during the hack.
4. Create the conda virtual environment by running the following command in your terminal from the repository root:

For Windows and Linux users:

```bash
conda env create -n tiger_hack -f codes/deploy/conda.yaml
```

For Mac users:

```bash
conda env create -n tiger_hack -f codes/deploy/conda_mac.yaml
```

### VSCode

1. If you already have an IDE setup in your system, you can skip this section
2. Install VSCode from [this website](https://code.visualstudio.com/download)
3. Install [Python](https://marketplace.visualstudio.com/items?itemName=ms-python.python) and [Jupyter](https://marketplace.visualstudio.com/items?itemName=ms-toolsai.jupyter) extensions from the VSCode marketplace
4. [Open](https://code.visualstudio.com/docs/editor/workspaces#_how-do-i-open-a-vs-code-workspace) the downloaded Source code folder in the VSCode

### Azure CLI

Azure CLI should be installed on the laptop to provide authentication to the Azure services.

1. Installation:
   Azure CLI can be installed by following the instructions in the below links:

   * Windows: [https://learn.microsoft.com/en-us/cli/azure/install-azure-cli-windows?tabs=azure-cli#install-or-update](https://learn.microsoft.com/en-us/cli/azure/install-azure-cli-windows?tabs=azure-cli#install-or-update)
   * Linux: [https://learn.microsoft.com/en-us/cli/azure/install-azure-cli-linux?pivots=apt#option-1-install-with-one-command](https://learn.microsoft.com/en-us/cli/azure/install-azure-cli-linux?pivots=apt#option-1-install-with-one-command)
   * Mac: [https://learn.microsoft.com/en-us/cli/azure/install-azure-cli-macos](https://learn.microsoft.com/en-us/cli/azure/install-azure-cli-macos)
2. Azure CLI Login:
   Execute the following commands in Powershell once Azure CLI is installed to log in to Azure using your credentials.

   ```bash
   az config set core.allow_broker=true
   az account clear
   az login
   ```

### Java

1. If you already have Java installed in your system, you can skip this step
2. Please download and install Java from [this website](https://www.java.com/en/download/manual.jsp)

## Update the configuration files

1. Populate relevant environment variables in [environment_variables.env](codes/configs/environment_variables.env)
2. Populate AI Studio project variables in [config.json](codes/config.json)

## Run the notebook

1. Sign in with Azure CLI before starting with running the notebook using the command and complete the login in the browser using the Azure ID that you want to use for the hack. If you are not sure what ID to use, please check with the support team available in the hack

   ```bash
   az login
   ```

2. Validate that you are logged in using the correct ID (the previous step prints the ID on your terminal along with other information)
3. Open the [end-to-end notebook](codes/notebooks/end_to_end.ipynb) in VSCode
4. Click on Select Kernel and select `tiger_hack` virtual environment. If you don't see `tiger_hack` in the Python Environments, please reload the VSCode and try again. If you still don't see the `tiger_hack`, please add it manually by locating the path where the environment is created. Please check with the support team available in the hack if you are not sure how to do this.
5. Run the cells in the notebook

## Launch the Chatbot

1. The code used in the notebook is also available as a Python package in the `codes/src` folder and can be installed in your environment. Activate the conda environment and install the package using the below commands

   ``` bash
   conda activate tiger_hack
   pip install -e codes/
   ```

2. The web chatbot can be launched using the following command.

   ``` bash
   cd codes
   streamlit run src/rag_ai_studio/app.py
   ```

We greatly value your feedback and welcome any suggestions for improvement. Please share your thoughts [here](https://forms.office.com/r/058CMXnXu6). You can also scan the QR code below to provide your feedback:

[![feedback form](codes/images/README/feedback.png "Feedback form")](https://forms.office.com/r/058CMXnXu6)

If you have any questions, please feel free to get in touch with us at <tigernlp@tigeranalytics.com>

## Additional References

* [Refer to this GitHub repository](https://github.com/Azure/aistudio-copilot-sample)

**Note**: The Azure service accesses used in this event are only valid during the event. Please contact your respective Microsoft account teams to follow up on the continued access or further questions.

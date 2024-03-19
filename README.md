# Tiger Analytics - Azure OpenAI Hackathon

This repository contains information (data, instructions for the workshop, and reference material) related to **Setting RAG solutioning using Azure AI services** conducted by Microsoft and Tiger Analytics.

Please clone this repository to your local system or download the zip by clicking on the green **Code** button, then on the **Download Zip** button and selecting the folder to download the zip to your local machine. Once the repository gets downloaded, extract the zip file by right-clicking on the file and selecting the **Extract** button.

1. The sample data that will be used during the session is available in the [data](data) folder. It also contains some sample Question and answers that can be asked on the dataset
2. The presentation that will be used during the session is available in the [references](references/AI_Build_Presentation.pdf) folder
3. Detailed instructions to follow during the session are available in the [instructions](instructions/ms_ai_build_steps.pdf) folder
4. Additional references can be found in the [references](references) folder

Please feel free to reach out to the trainers during the session, for any questions or issues related to access or the
solution. We hope you have a rewarding experience during the hack event.

**Note**: The Azure service accesses used in this event are only valid during the event. Please contact your respective Microsoft account teams to follow up on the continued access or further questions.


## Prerequisites
### Operating System
Windows and Linux are the preferred operating systems for the hack event. They’re preferred as the tools, libraries are tested in Windows and Linux. Macbooks can be used if there are no alternatives, but challenges are to be expected.

### Python Environment
Python version **3.9** should be installed on the laptops used for the hack.
Refer to the instructions below to install Miniconda CLI and create a Python 3.9 environment.
1. Install Miniconda CLI following the documentation: https://docs.anaconda.com/free/miniconda/#quick-command-line-install

2. Create a conda virtual environment:
  conda create --name hack python=3.9
3. Install the dependencies:
   ```bash
   pip install -r codes/deploy/requirements.txt
   ```

### Azure CLI
Azure CLI should be installed on the laptop to provide authentication to the Azure services.

1. Installation guide
   
  Windows: https://learn.microsoft.com/en-us/cli/azure/install-azure-cli-windows?tabs=azure-cli#install-or-update

  Linux: https://learn.microsoft.com/en-us/cli/azure/install-azure-cli-linux?pivots=apt#option-1-install-with-one-command

2. Azure CLI Login:
  Execute the following commands once Azure CLI is installed to login to Azure using your credentials.
  ```bash
  az config set core.allow_broker=true
  az account clear
  az login
  ```

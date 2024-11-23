# Azure_AI_P-S-13

# AI Document Intelligence App

This repository contains code and resources for building an AI-powered Document Intelligence application using Azure AI services. The application extracts data from forms using a custom-trained machine learning model, leveraging Azure's AI Document Intelligence capabilities to automate data processing from documents.

## Project Overview

The goal of this project is to automate the data entry process from purchase order sheets by using AI services to extract structured data, which can then be used to update a database. This solution uses Azure AI Document Intelligence to extract text, key/value pairs, and tables from forms.

## Features

- Utilizes **Azure AI Document Intelligence** for automated document processing.
- Extracts structured data like key/value pairs and tables from forms.
- Supports custom model training for specialized forms.
- Integrated with Azure Blob Storage for storing training data.

## Prerequisites

To set up and run this project, you need the following:

- [Visual Studio Code](https://code.visualstudio.com/) installed.
- [Azure CLI](https://learn.microsoft.com/en-us/cli/azure/install-azure-cli) installed.
- An [Azure subscription](https://azure.microsoft.com/free/) with appropriate permissions.
- [Git](https://git-scm.com/) for cloning the repository.

## Getting Started

### Clone the Repository

To start, clone this repository to your local machine:

```bash
git clone https://github.com/MicrosoftLearning/mslearn-ai-document-intelligence.git
```

### Install Required Extensions

Open Visual Studio Code and make sure to install any recommended extensions for your language of choice (C# or Python).

### Azure AI Document Intelligence Setup

1. **Create Azure Resources:**
   - Log into the [Azure portal](https://portal.azure.com/).
   - Search for and create a new **Azure AI Document Intelligence** resource.
   - Choose your subscription, create a new resource group (e.g., `DocIntelligenceResources`), and select a region.
   - Use a unique name and choose the  pricing tier if available.

2. **Create a Blob Storage Container:**
   - Follow the instructions to run the `setup.cmd` file, which creates a storage account and uploads the training files.

3. **Training the Model:**
   - Use the [Document Intelligence Studio](https://documentintelligence.ai.azure.com/studio) to train your custom model with the uploaded data.

### Environment Configuration

Update the configuration settings:

1. **Open Environment File:**
   - Edit the `.env` file (Python) or `appsettings.json` (C#) with the following details:
     - `DOC_INTELLIGENCE_ENDPOINT` - Your Document Intelligence endpoint URL.
     - `DOC_INTELLIGENCE_KEY` - Your Document Intelligence key.
     - `MODEL_ID` - The unique Model ID generated during training.

2. **Run the Application:**
   - Install dependencies using the following commands:
   
     ```bash
     # For Python
     pip install azure-ai-formrecognizer==3.3.3
     ```
   - Execute the application:

     ```bash
     # For Python
     python test-model.py
     ```

## Project Structure

The repository contains the following folders and files:

```
mslearn-ai-document-intelligence/
│
├── Labfiles/
│   └── 02-custom-document-intelligence/
│       ├── CSharp/                   # Contains C# implementation files
│       ├── Python/                   # Contains Python implementation files
│       └── sample-forms/             # Sample form images and JSON label files
│
├── .env                              # Environment file for Python (API keys and endpoint)
├── setup.cmd                         # Script to set up Azure Blob Storage
└── README.md                         # This README file
```

## Testing

After running the application, observe the structured output in the console, displaying field names and values extracted from the form, such as:

```
-------- Analyzing document #1 --------
Document has type: Invoice
Document confidence: 0.95
Found field 'Merchant' with value 'XYZ Corporation' and confidence: 0.98
Found field 'CompanyPhoneNumber' with value '+1-800-123-4567' and confidence: 0.96
...
```

## Resources

- [Azure AI Document Intelligence Documentation](https://learn.microsoft.com/en-us/azure/ai-services/document-intelligence/)
- [Azure Blob Storage Documentation](https://learn.microsoft.com/en-us/azure/storage/blobs/)

## License

This project is licensed under the MIT License.

![Screenshot 2024-11-23 150345](https://github.com/user-attachments/assets/ac723804-64a8-43b5-b953-8bafd3a8b8ec)

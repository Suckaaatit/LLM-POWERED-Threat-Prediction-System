

---

# **LLM-Powered Threat Prediction System**  
An AI-powered threat modeling tool that leverages Large Language Models (LLMs) to generate threat models and attack trees for a given application based on the STRIDE methodology. Users provide application details, such as the application type, authentication methods, and whether the application is internet-facing or processes sensitive data. The model then generates its output based on the provided information.  


<img width="665" height="373" alt="image" src="https://github.com/user-attachments/assets/07d16fc4-3837-4fb0-9b51-9f107cf849c2" />


## **Table of Contents**  
- [Features](#features)  
- [Roadmap](#roadmap)  
- [Installation](#installation)  
- [Usage](#usage)  

## **Features**  
- Simple and user-friendly interface  
- Generates threat models based on the STRIDE methodology  
- Multi-modal: Use architecture diagrams, flowcharts, etc., as inputs for threat modeling  
- Generates attack trees to enumerate possible attack paths  
- Suggests possible mitigations for identified threats  
- Supports DREAD risk scoring for identified threats  
- Generates Gherkin test cases based on identified threats  
- 🆕 GitHub repository analysis for comprehensive threat modeling  
- No data storage; application details are not saved  
- Supports models accessed via OpenAI API, Azure OpenAI Service, Google AI API, Mistral API, or locally hosted models via Ollama and 🆕 LM Studio Server  
- Available as a Docker container image for easy deployment  
- Environment variable support for secure configuration  

## **Roadmap**  
- [ ] Add support for multi-modal threat modeling  
- [ ] Autogenerate application descriptions based on README files in GitHub repositories  
- [ ] Customizable and exportable reports (e.g., PDF, Word) that include the generated threat model, attack tree, and mitigations  
- [ ] Add a helper tool to guide users to create effective application descriptions before generating threat models  
- [ ] Update UI to support multiple languages  

## **Installation**  

### **Option 1: Cloning the Repository**  

1. Clone this repository:  
    ```bash
    git clone <repository-link>
    ```
2. Change to the cloned repository directory:  
    ```bash
    cd <repository-name>
    ```
3. Install the required Python packages:  
    ```bash
    pip install -r requirements.txt
    ```
4. Set up environment variables:  

   a. Copy the `.env.example` file to a new file named `.env`:  
   ```bash
   cp .env.example .env
   ```
   b. Edit the `.env` file to add your API keys and/or endpoint URLs:  
   ```bash
   GITHUB_API_KEY=your_actual_github_api_key
   OPENAI_API_KEY=your_actual_openai_api_key
   ANTHROPIC_API_KEY=your_actual_anthropic_api_key
   AZURE_API_KEY=your_actual_azure_api_key
   AZURE_API_ENDPOINT=your_actual_azure_endpoint
   AZURE_DEPLOYMENT_NAME=your_actual_azure_deployment_name
   GOOGLE_API_KEY=your_actual_google_api_key
   MISTRAL_API_KEY=your_actual_mistral_api_key
   OLLAMA_ENDPOINT=http://localhost:11434
   LM_STUDIO_ENDPOINT=http://localhost:1234
   ```

### **Option 2: Using Docker Container**  

1. Pull the Docker image from Docker Hub:  
    ```bash
    docker pull <docker-image-name>
    ```
2. Create a `.env` file with your API keys as described in step 4 of Option 1.  

## **Usage**  

### **Option 1: Running the Streamlit App Locally**  

1. Run the Streamlit app:  
    ```bash
    streamlit run main.py
    ```
2. Open the app in your web browser using the provided URL.  
3. Follow the steps in the Streamlit interface to use the application.  

### **Option 2: Using Docker Container**  

1. Run the Docker container, mounting the `.env` file:  
    ```bash
    docker run -p 8501:8501 --env-file .env <docker-image-name>
    ```
    This command will start the container, map port 8501 (default for Streamlit apps) from the container to your host machine, and load the environment variables from the `.env` file.  

2. Open a web browser and navigate to `http://localhost:8501` to access the app running inside the container.  
3. Follow the steps in the Streamlit interface to use the application.  

**Note:** When you run the application (either locally or via Docker), it will automatically load the environment variables you've set in the `.env` file. This will pre-fill the API keys in the application interface.  




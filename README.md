**Customer Support AI Agent**

## **Introduction**  

This project is an AI-powered Gmail customer service agent built using LangChain, LangGraph, and ChromaDB. It follows a multi-agent RAG (Retrieval-Augmented Generation) architecture to automate email-based customer support. I built this to address the high cost and inefficiency of traditional support systems. The agent can handle multiple user queries at once, reply empathetically, and maintain consistent communication. It’s ideal for businesses looking to reduce support overhead, scale their response system, and improve customer satisfaction through intelligent automation.

## **Features**  

Automated Email Handling – Automatically reads and responds to customer emails with relevant, accurate, and empathetic replies.

Multi-Agent RAG Architecture – Uses multiple specialized agents and Retrieval-Augmented Generation for better context understanding and response quality.

Parallel Query Handling – Can handle multiple user queries simultaneously, ensuring fast and scalable customer support.

Context-Aware Responses – Retrieves relevant information from the knowledge base to provide accurate, situation-specific answers.

No Training Cost – Eliminates the need for human training, reducing operational costs significantly.

Customizable and Expandable – Can be fine-tuned with company-specific data to match tone, branding, or specialized support needs.

## **How It Works**  

1. **Email Monitoring**: The agent constantly keeps checking for new emails in company.
2. **Email Categorization**: The agent sorts each email into predefined categories.  
3. **Response Generation**:   
   - **For complaints or feedback**: The system quickly drafts a tailored email response.  
   - **For service/product questions**: The system uses RAG to retrieve **accurate information** from agency documents and generates a response.  
   - **For unrelated emails**: It skips emails that are unrelated to customer service.  
4. **Quality Assurance**: Each draft email undergoes quality checking by a proofreading agent. 
5. **Sending**: Once an email gets approved, it is sent to the client imediately. 

## System Flowchart
I have provided the flow graph diagram in `workflow.png`.

## Tech Stack

* Python, LangChain, LangGraph, ChromaDB, FastAPI
* A multi-agent RAG architecture leveraging pre-trained LLMs
* The retrieval-augmented generation (RAG) approach to ensure relevant responses based on past conversations and company policies.
* Google Gmail API

## How to Run

### Setup

1. **Clone the repository:**

   ```sh
   git clone {github-link}
   cd langgraph-email-automation
   ```

2. **Create and activate a virtual environment:**
   
   ```sh
   python -m venv venv
   venv\\Scripts\\activate #For Windows
   ```

3. **Install the required packages:**

   ```sh
   pip install -r requirements.txt
   ```

4. **Set up environment variables:**

   Create a `.env` file in the root directory of the project. Add your EMAIL ID and GOOGLE API KEY for Gemini.

   ```env
   MY_EMAIL=your_email@gmail.com
   GOOGLE_API_KEY=your_gemini_api_key
   ```

5. **Ensure Gmail API is enabled:**

   Follow [this guide](https://developers.google.com/gmail/api/quickstart/python) to activate the Gmail App.
   Make sure to get the `credentials.json` file.

### Running the Application

**Start the workflow:**

   ```sh
   python main.py
   ```

### Customization

Agent Behaviour can be modified from `nodes.py` file.
Prompt templates can be modified from the `prompts.py` file.

You can also add your own agency data into the `data` folder, then you must create your own vector store by running:

```sh
python add_data.py
```
Do not forget to update the data folder path.
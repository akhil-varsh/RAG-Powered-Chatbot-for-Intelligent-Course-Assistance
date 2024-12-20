# RAG-Powered Chatbot for Intelligent Course Assistance 🤖📚

This project implements a **RAG (Retrieve and Generate)**-based chatbot designed to assist with course-related queries. The system utilizes **OCI Generative AI** services for generating responses and **Cohere Embeddings** for document retrieval. The chatbot is built using the **LangChain** framework and is deployed on an **OCI Virtual Machine** for production.

## Features ✨

- **Context-Aware Responses**: The chatbot generates accurate responses using the **Cohere Command Model**. 🤖
- **Efficient Document Search**: Embeddings are created using **Cohere Embed English V3.0**, and **ChromaDB** is used for fast document retrieval. 🔍
- **User-Friendly Interface**: The chatbot is integrated with a **Streamlit** interface for smooth user interaction. 💬
- **Deployment**: The chatbot is deployed on **OCI Virtual Machine** for scalable production use. ☁️

## Technologies Used 🛠️

- **LangChain**: Framework for building the RAG-based chatbot. 🦜🔗
- **OCI Generative AI Service**: Provides the AI models for both generation and embedding. 🌐
- **Cohere**: Used for embedding and generating context-aware responses. 📖
- **ChromaDB**: A vector store used for storing embeddings and performing fast document searches. 📊
- **Streamlit**: Interactive web app framework for user interaction. 🌈
- **Python**: The main programming language for the chatbot implementation. 🐍
- **OCI Virtual Machine**: Deployed on an OCI Ubuntu VM for production use. 💻

## Installation 🔧

### Prerequisites 📝

- Python 3.7 or higher
- Oracle Cloud Infrastructure account with access to **Generative AI services**

### Setup ⚙️

1. Clone the repository:
    ```bash
    git clone https://github.com/akhil-varsh/RAG-Powered-Chatbot-for-Intelligent-Course-Assistance.git
    cd RAG-Powered-Chatbot
    ```

2. Install the required dependencies:
    ```bash
    pip install -r requirements.txt
    ```

3. Run the **document loader script** to preprocess and embed documents:
    ```bash
    python document_loader.py
    ```

4. Launch the Streamlit app to interact with the chatbot:
    ```bash
    streamlit run app.py
    ```

5. Open the provided URL to chat with the **RAG-powered course assistant**.

## Code Explanation 📝

### Document Loader (`document_loader.py`) 📥

This script loads, splits, and processes the documents. The steps involved are:

1. **Document Loading**: It loads PDF documents from a specified directory (`./pdf-docs`). 📑
2. **Text Splitting**: The documents are split into smaller chunks (max 2500 characters per chunk) for embedding. ✂️
3. **Embeddings**: The script uses **OCI Generative AI Embeddings** to create embeddings for the documents. 🔐
4. **Batch Processing**: Documents are processed in batches of 96 due to the API limit. 📦
5. **Vector Store**: The embeddings are stored in **ChromaDB** for fast retrieval. 🏃‍♂️

### Streamlit App (`app.py`) 💻

This is the web interface where users interact with the chatbot. Key components of the app include:

1. **Chain Setup**: The `create_chain()` function sets up a **ConversationalRetrievalChain** that connects the language model and document retriever. 🔗
2. **Chat Function**: The `chat()` function processes user input, retrieves relevant documents, and generates a response using the **OCI Generative AI** model. 💬
3. **Streamlit UI**: The app uses **Streamlit** to display the chatbot interface. Users input questions, and the app displays both the question and the AI-generated response. 🌟

### Example Usage 📌

1. The user inputs a question about a course. 📝
2. The chatbot retrieves relevant documents based on the input. 📄
3. The **OCI Generative AI Service** generates an accurate response. 🧠
4. The chatbot displays the response along with any source references (e.g., page numbers from the documents). 🔖

## Contributing 🤝

1. Fork the repository.
2. Create a new branch (`git checkout -b feature-name`).
3. Commit your changes (`git commit -am 'Add feature'`).
4. Push to the branch (`git push origin feature-name`).
5. Create a new Pull Request.

## License 📜

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgements 🙏

- **Cohere** for providing the powerful **Command Model** and **Embedding API**. 🧑‍💻
- **LangChain** for simplifying the RAG framework integration. 🦜🔗
- **OCI** for cloud services supporting AI deployment. ☁️
- **Streamlit** for enabling easy web app creation. 🌟

---

<p align="center">
  Made with ❤️ by Akhil
</p>

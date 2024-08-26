# LLM-Chatbot-using-pre-trained-model
The primary goal of this capstone project is to develop an industry-specific Large Language Model (LLM) Bot using pre-trained models from platforms such as Hugging Face.
Importing Libraries:

Various libraries are imported to handle PDF loading, text processing, embedding generation, vector storage, and creating a conversational retrieval chain.

1. PDF Loading:
The script loads a PDF document using the PyPDFLoader, which extracts text from the PDF for further processing.

2. Text Splitting:
The extracted text is split into chunks of a specified size using RecursiveCharacterTextSplitter. This ensures that the document is broken into manageable pieces for embedding.

3. Embeddings Creation:
The script generates embeddings for the text chunks using a pre-trained model (sentence-transformers/all-MiniLM-L6-v2) from HuggingFace. Embeddings are numerical representations of the text that allow the model to understand semantic similarities between different text pieces.

3. Vector Store Creation:
A FAISS vector store is created from the embeddings. This allows for efficient similarity search, enabling the model to retrieve relevant chunks of text in response to user queries.

4. Language Model Setup:
A language model is initialized using CTransformers. The model TheBloke/Llama-2-7B-Chat-GGUF is used for generating human-like text responses.

5. Conversational Retrieval Chain:
A ConversationalRetrievalChain is set up to handle the interaction. This chain takes the user's question, retrieves relevant text chunks from the vector store, and generates a coherent response based on the retrieved information and conversation history.

6. Conversation Handling Functions:
The conversation_chat function manages the conversation logic, handling user queries and updating the conversation history.
The handle_submit function deals with the user input and updates the conversation history accordingly.

7. Gradio Interface:
The gr.Blocks() function defines the web interface using Gradio. It includes a markdown title, input textbox, and a submit button. The interface also handles displaying the chat history and processing user inputs.

8. Launching the Interface:
The demo.launch() command launches the Gradio interface, allowing users to interact with the AI directly through a web-based application.

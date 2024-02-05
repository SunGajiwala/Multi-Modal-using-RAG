# Conversational Agent with LangChain, OpenAI API, and RAG Concept

## Project Overview

This project is a conversational agent that leverages LangChain, OpenAI API, and the RAG (Retrieval-Augmented Generation) concept. The agent is designed to read lengthy PDF documents, extract various components such as text, images, and tables, and store them in a vector database for efficient retrieval during conversations with users.

## Features

- **PDF Processing**: The agent is capable of parsing and extracting information from long PDF documents.
  
- **Multi-Modal Extraction**: Extracts text, images, and tables from PDFs for a comprehensive understanding.

- **Vector Database**: Utilizes a vector database to store and retrieve information efficiently.

- **Conversational AI**: Implements the RAG concept to enhance conversational interactions with users.

## Multi-Modal RAG

- We will use Unstructured to parse images, text, and tables from documents (PDFs).

- We will use the multi-vector retriever with Chroma to store raw text and images along with their summaries for retrieval.

- We will use GPT-4V for both image summarization (for retrieval) as well as final answer synthesis from join review of images and texts (or tables).

## Dependencies

- [LangChain](https://python.langchain.com/docs/get_started/installation) <- Visit here to understand langchain installation

- [OpenAI API](https://platform.openai.com/docs/quickstart?context=python) <- Instructions for setting up and using OpenAI API.

- [Chroma DB](https://docs.trychroma.com/getting-started) <- Instructions for setting up and using the vector database.

## Usage

1. Provide path to the source pdf

2. Change the prompt_text according to your needs.

3. Replace your questions in the query line.

3. The agent will use the stored information for intelligent responses.

## Considerations

1. Retrieval

    Retrieval is performed based upon similarity to image summaries as well as text chunks.
    This requires some careful consideration because image retrieval can fail if there are competing text chunks.
    To mitigate this, I produce larger (4k token) text chunks and summarize them for retrieval.

2. Image Size

    The quality of answer synthesis appears to be sensitive to image size, as expected.
    I'll do evals soon to test this more carefully.

## License

This project is licensed under the [MIT License](LICENSE.md).

## Acknowledgments

- Thanks to [LangChain](link-to-langchain) for providing the language processing capabilities.
- Thanks to [OpenAI](link-to-openai) for the powerful language model.
- Thanks to [Vector DB](link-to-vector-db) for efficient data storage.

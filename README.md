# Hugging Face API Document Summarizer (MATLAB Application)

This MATLAB application demonstrates how to download, process, and summarize long documents using the Hugging Face API. The application is divided into several steps:

## Steps

### 1. Read an HTML File
The code fetches a document from a URL (e.g., from Project Gutenberg or arXiv) and extracts the plain text from the HTML format.

### 2. User Settings
Users need to provide their Hugging Face API key and define the maximum chunk size for splitting the document.

### 3. Helper Functions

- **`summarizeTextHuggingFace`**: A function that uses the Hugging Face API to summarize text. It sends the text to a specified model (e.g., `pegasus-xsum`) and returns the summary.
  
- **`createChunks`**: A function that splits long text into manageable chunks, each with a defined character limit, to ensure that each chunk can be processed by the summarization API.

### 4. Download and Preprocess the Long Document
The application fetches the document from the specified URL and extracts the plain text from the HTML content.

### 5. Split Long Text into Chunks
The long text is divided into smaller chunks, each with a specified maximum character count, making it easier to summarize.

### 6. Summarize Each Chunk
The application iterates over the chunks and sends them to the Hugging Face API for summarization, with a pause between requests to prevent overloading the server and triggering errors (e.g., 503 errors due to rate limits).

### 7. Combine Final Summary
After each chunk is summarized, the individual summaries are joined to create a final cohesive summary of the entire document.

## Conclusion
This approach ensures that even large documents can be effectively processed and summarized in manageable portions, leveraging the power of the Hugging Face API within MATLAB.

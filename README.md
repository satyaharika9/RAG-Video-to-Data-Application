# RAG Application for YouTube Video Processing

This project demonstrates the use of Retrieval-Augmented Generation (RAG) for extracting relevant information from a YouTube video. The application downloads a YouTube video, extracts its images, audio, and text. By leveraging advanced techniques like LlamaIndex and LanceDB, this project allows for efficient querying of the extracted content based on both similarity search and chunked text retrieval.Queries use similarity-based retrieval techniques to return the most relevant sections of text or images by comparing embeddings of the query with pre-calculated document and image embeddings.

## How It Works:

### YouTube Video Download and Processing:
Using yt-dlp, the video is downloaded from YouTube, and MoviePy extracts frames, audio, and metadata from the video.

### Audio Transcription:
The audio from the video is extracted using MoviePy and then transcribed into text using OpenAI Whisper or SpeechRecognition for querying.

### Text and Image Embedding:
Sentence Transformers are used to generate text embeddings for the extracted transcriptions.
CLIP generates image embeddings for the extracted frames, allowing multimodal retrieval.

### Indexing with LlamaIndex and LanceDB:
The extracted text and images are indexed using LlamaIndex. The embeddings and metadata are stored in LanceDB, allowing efficient similarity search and retrieval based on the user’s query.

### Query and Retrieval:

A query is inputted by the user, and the system compares the query embedding to the stored embeddings.
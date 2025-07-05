# Shazam for Subtitles

## Improve Subtitle Search Relevance Using NLP and Machine Learning

Enhance the search engine experience by improving subtitle search accuracy using semantic search and natural language processing techniques.

**Features:**
- **Semantic Search Engine**: Understands the meaning and context of queries for more relevant subtitle results.
- **Keyword-based Search Engine**: Retrieves subtitles based on exact keyword matches.
- **Subtitle Retrieval**: Leverages cosine similarity for fast and accurate subtitle retrieval.
- **Document Chunking**: Divides large subtitle documents into manageable chunks to prevent information loss.

### How to Use

#### Open in Colab

Open the project notebook in Google Colab and follow the step-by-step instructions.

[Open the Colab Notebook](https://colab.research.google.com/drive/1CUYInxLkvdPgwKdv7H_4ruk05uh3BSfE?usp=sharing)

- A **Cloud GPU** will be assigned to you to run the notebook code for retrieving and processing subtitles.

#### Features
- **Vectorization of Subtitle Documents**: Use BERT or TF-IDF for generating document embeddings.
- **Audio Query Processing**: Convert audio queries into embeddings for accurate subtitle retrieval.
- **Cosine Similarity Calculation**: Measure document relevance with cosine similarity between the query and subtitle document embeddings.
- **Document Chunking**: Efficiently handle large subtitle files by chunking them into smaller, meaningful pieces.

### Core Logic

1. **Preprocessing**:
   - Clean subtitle documents by removing irrelevant data such as timestamps.
   - Apply necessary cleaning steps to improve text quality.
  
2. **Vectorization**:
   - **BOW/TFIDF**: Good for keyword-based searches.
   - **BERT SentenceTransformers**: Ideal for semantic-based search engines.

3. **Cosine Similarity**:
   - Compute similarity between the user query vector and document vectors.
   - Return the most relevant subtitles based on similarity scores.

4. **Chunking**:
   - Split long subtitle documents into smaller chunks to avoid information loss.
   - Use overlapping windows to maintain context.

### Models Used

#### Whisper Model for Audio Transcription
The **Whisper model** from OpenAI is used for transcribing audio queries into text, enabling the search engine to process queries in natural language. This model allows for both **English transcription** and **non-English transcription** using auto-detection or by selecting the source language of the audio.

#### Embedding with SentenceTransformers

For semantic search, **HuggingFaceEmbeddings** with the **Sentence-Transformers** model is used. This model helps convert subtitle content into dense vector representations, which are then compared to the query embeddings to find the most relevant results. The use of this embedding model enables better context understanding and accurate subtitle retrieval based on meaning rather than just keyword matches.

#### Document Chunking

To handle large subtitle files efficiently, the text is split into smaller, manageable chunks. This process, known as **document chunking**, prevents information loss when processing large text data and ensures that the context of the text is maintained. The chunks are created with overlapping windows to ensure no context is lost between adjacent sections.

### Save Subtitles in SRT Format
- Subtitle search results are saved in the **SRT** format for easy use in video players and captioning systems.

### Data

The database contains a sample of 82,498 subtitle files from **opensubtitles.org**. These subtitles are primarily for movies and TV-series released between 1990 and 2024.

- **Database File Name**: `eng_subtitles_database.db`
- **Table Name**: `zipfiles`
- **Columns**:
  1. **num**: Unique Subtitle ID reference for [www.opensubtitles.org](https://www.opensubtitles.org).
  2. **name**: Subtitle File Name.
  3. **content**: Subtitle file stored in binary format using 'latin-1' encoding.

You can use the **num** column to get more details about each subtitle by visiting the following URL:  
`https://www.opensubtitles.org/en/subtitles/{num}`  
*Replace `{num}` with the Unique Subtitle ID.*

### Example Usage

- **Transcribe and Search Subtitles**: Transcribe subtitles based on audio queries and retrieve the most relevant documents using semantic search.
- **Audio Query Search**: Provide a minimum of a **2-minute** audio clip from a movie/TV series, and search for matching subtitles using cosine similarity.


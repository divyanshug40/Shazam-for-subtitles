# Enhancing Search Engine Relevance for Video Subtitles (Cloning Shazam)

![Project Icon](https://img.icons8.com/ios/452/search.png)

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

- A **Cloud GPU** will be assigned to you to run the notebook code for retrieving and processing subtitles.

![Google Colab Icon](https://img.icons8.com/ios/452/google-colab.png)

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

#### Save Subtitles in SRT Format
- Save subtitle search results in the following formats: SRT

#### Data

![Subtitle Data Icon](https://img.icons8.com/ios/452/database.png)

Click the icon above to download the subtitle data.

#### Example Usage

- **Transcribe and Search Subtitles**: Transcribe subtitles based on audio queries and retrieve the most relevant documents using semantic search.
- **Audio Query Search**: Provide a minimum of 2-minute audio clip from a movie/TV series, and search for matching subtitles using cosine similarity.


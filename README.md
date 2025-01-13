# Neo4j-Langchain-Knowledge_Graph
Using Neo4j and Langchain for Knowledge Graph Creation

## Key Features

1. **Dependency Installation**:
   The notebook installs the required libraries:
   - `python-dotenv` for managing environment variables.
   - `langchain_community` for LangChain integration.
   - `neo4j` for interacting with the database.
   - `openai` for language models.
   - `pypdf` for loading PDFs.
   - `tiktoken` for handling embeddings.

2. **PDF Processing**:
   - Loads a PDF document.
   - Splits the document into manageable chunks for analysis.

3. **Neo4j Integration**:
   - Connects to a Neo4j database using credentials stored in a `.env` file.
   - Creates and stores vector embeddings in Neo4j for the PDF chunks.
   - Establishes relationships between chunks and the source PDF.

4. **Embedding Creation**:
   - Generates embeddings for text chunks using OpenAI.
   - Stores these embeddings in the Neo4j database.

5. **Query and Analysis**:
   - Creates a question-answering chain using stored data.
   - Returns insights about the main topic of the PDF.
   - Updates and verifies the Neo4j database schema.

6. **Neo4j Structure Visualization**:
   - Displays indexes and relationships among nodes in the database.

## Requirements

- **Python Libraries**:
  Ensure the following libraries are installed:
  - `python-dotenv`
  - `langchain_community`
  - `neo4j`
  - `openai`
  - `pypdf`
  - `tiktoken`

- **Neo4j Database**:
  - A Neo4j database configured with a URI, username, and password specified in a `.env` file.

- **OpenAI Credentials**:
  - A valid API key for accessing OpenAI services.

## Usage

1. **Initial Setup**:
   - Create a `.env` file with the following variables:
     ```env
     NEO4J_URI=bolt://<your_neo4j_host>:7687
     NEO4J_USERNAME=<your_username>
     NEO4J_PASSWORD=<your_password>
     OPENAI_API_KEY=<your_openai_api_key>
     ```

2. **Notebook Execution**:
   - Ensure all required packages are installed.
   - Replace the PDF path (`/content/data.pdf`) with your own file path.

3. **Queries and Visualizations**:
   - Run the cells to create vectors, store them in Neo4j, and perform queries.

## Example Workflow

- **Add a PDF to the Database**:
  The notebook loads a PDF file, splits it into chunks, and stores information as nodes in a graph.

- **Create Relationships in Neo4j**:
  Relationships such as `PART_OF` are created to connect chunks to the source PDF.

- **Ask the Model Questions**:
  The model answers questions like "What is the main topic of this PDF?" based on the processed data.

## Notable Outputs

- Main topic of the PDF:
  ```plaintext
  The main topic of this PDF document is the annual report on new drug therapy approvals by the FDA's Center for Drug Evaluation and Research (CDER).

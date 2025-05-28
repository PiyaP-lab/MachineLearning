# 📐 Architecture: AI-Powered Test Case Generator with Streamlit + Squash + RAG

```mermaid
flowchart TD
    A[Streamlit Web App<br>(User Interface)] --> B{Input Type}
    B --> B1[Manual / CSV Input<br>(Req ID, Title, Desc)]
    B --> B2[Squash API (GET)<br>Fetch Requirements]

    B1 --> C[Embedding Model<br>(OpenAI / Custom)]
    B2 --> D[Squash API (POST)<br>Push Test Case]

    C --> E[Vector Database<br>(Stores embeddings)]
    E --> F[Retrieval-Augmented Generation Engine<br>(RAG combines context with GPT model)]
    F --> G[Gherkin Feature<br>Output + Display]

    G --> H[Push Button Logic]
    H --> D

    F --> D

    H --> I[Bulk Push Handler]
    I --> D

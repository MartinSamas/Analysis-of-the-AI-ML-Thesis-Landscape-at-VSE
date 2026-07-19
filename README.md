# Analysis-of-the-AI-ML-Thesis-Landscape-at-V-E
This project provides a data-driven analytical study of 55 bachelor theses from the VŠKP catalog to map the Artificial Intelligence and Machine Learning landscape at the Faculty of Informatics and Statistics. The insights are structured to guide decisions regarding curriculum development, student recruitment, and industry partnerships.

## Data Collection & Preprocessing
* **Corpus Generation:** Scraped 55 unique bachelor theses from the VŠKP portal's English interface, capped at 15 results per query to prevent topic distortion.
* **Target Queries:** "natural language processing", "sentiment analysis", "transformer", and "large language model".
* **Schema Extraction:** Extracted multi-layered metadata including textual elements (title, abstract, keywords), institutional context, temporal tracking (2014-2026), and academic network details.
* **Cleaning:** Resolved HTML entities, normalized study program tags, and filtered the dataset to strictly include English abstracts to ensure semantic alignment.

## Methodology
* **Semantic Embedding:** Applied the pre-trained `all-MiniLM-L6-v2` SentenceTransformer to generate 384-dimensional dense vectors representing the combined title, abstract, and keywords of each thesis.
* **Clustering:** Partitioned the thematic space using K-means clustering (k=5), chosen for interpretability and thematic stability rather than silhouette score optimization.
* **Dimensionality Reduction:** Used UMAP to project high-dimensional latent space into 2D coordinates for visual mapping.
* **Feature & Entity Extraction:** Utilized c-TF-IDF for cluster labeling, and built custom regex-based classifiers to extract application domains and technology mentions.
* **Network Analysis:** Constructed a bipartite graph connecting supervisors to topic clusters, applying greedy modularity communities to map faculty expertise.

## Analytical Views & Key Findings
* **Thematic Map:** Identified 5 primary research pillars: Sentiment Analysis & Social Text Analytics (n=19), LLM Systems (n=11), Applied ML & Multimodal Systems (n=10), Misinformation & Content Integrity (n=8), and Conversational AI (n=7).
* **Study Program Profile:** Applied Informatics shows broad adoption across all clusters. Data Analytics strongly favors structured, experimental work (Applied ML and Misinformation), indicating a need for ML tooling depth rather than basic LLM application courses.
* **Application Domains:** Heavy focus on NLP and Social Media/Marketing. There is a significant, addressable gap in high-demand industry applications like Finance and Healthcare.
* **Technology Landscape:** Commercial LLM APIs dominate student usage. Classic ML frameworks (PyTorch, scikit-learn, TensorFlow) are nearly absent, signaling a shift from model-building to tool deployment.
* **Research Depth:** The Applied ML and Misinformation clusters consist exclusively of original/experimental work, whereas LLM Systems feature the highest share of tool deployment.
* **Supervisor Expertise Network:** Thesis supervision is highly concentrated among a few individuals. Growing fields like Conversational AI lack a dedicated faculty champion, presenting a capacity risk for future curriculum expansion.

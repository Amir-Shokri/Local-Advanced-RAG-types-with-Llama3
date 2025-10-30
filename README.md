<div align="center">

<div style="margin: 20px 0;">
  <img src="./assets/logo2.png" width="180" height="180"  style="border-radius: 20px; box-shadow: 0 8px 32px rgba(0, 217, 255, 0.3);">
</div>

# Local-Advanced-RAG-types-with-Llama3


<div align="center">
  <img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&size=28&duration=3000&pause=1000&color=c709dcff&center=true&vCenter=true&width=600&lines=Welcome+to+Advanced+RAG+types;with+Local+Llama3" alt="Typing Animation" />
</div>

---
<div align="left">

# Summary 

<p align="justify"> 

  
  The project explores advanced retrieval-augmented-generation (RAG) methods implemented locally using Llama 3. It implements several types of advanced **RAG** workflows including _Multi-Query_, _RAG-Fusion_, _Answer Individually_, _Answer Recursively_, and _Hypothetical Document Embeddings (HyDE)_. The **Multi-Query** method generates multiple queries from a single user prompt to retrieve a richer set of documents.  **RAG-Fusion** uses multiple generated queries plus a “Reciprocal Rank Fusion” style combining of results to improve retrieval relevance. The **recursive** method interleaves reasoning and **retrieval** in steps (reason → retrieve → reason) for complex, multi-step questions.  And **HyDE** uses a generated hypothetical document embedding to perform zero‐shot dense retrieval without labelled relevance data. 
  
  </p>

<div style="margin: 20px 0;">
  <img src="./assets/HyDE2.png" width="800" height="600"  style="border-radius: 20px; box-shadow: 0 8px 32px rgba(0, 217, 255, 0.3);">
  
</div>


<div align="left">

---
  
## Types of Advanced RAG:
### Query Transformations

- [Multi-Query](#multi-query)
- [RAG-Fusion](#RAG-Fusion)
- [Answer recursively](#Answer-recursively)
- [Answer individually](#Answer-individually)
- [Hypothetical Document Embeddings (HyDE)](#Hypothetical-Document-Embeddings-HyDE)


---
### [Multi-Query](LocalRAG_MultiQuery_LLama3_Nvidia_Stocks.ipynb)
<p align="justify"> 
The Multi-Query automates the process of prompt tuning by using an LLM to generate multiple queries from different perspectives for a given user input query. For each query, it retrieves a set of relevant documents and takes the unique union across all queries to get a larger set of potentially relevant documents. By generating multiple perspectives on the same question, the MultiQueryRetriever can mitigate some of the limitations of the distance-based retrieval and get a richer set of results.  </p>


<div style="margin: 20px 0;">
  <img src="./assets/Multi-Query1.png" width="1747" height="600"  style="border-radius: 20px; box-shadow: 0 8px 32px rgba(0, 217, 255, 0.3);">
  
</div>


---

### [RAG-Fusion](LocalRAG_RAGFusion_LLama3_Nvidia_Stocks.ipynb)
<p align="justify"> 
RAG-Fusion, a search methodology that aims to bridge the gap between traditional search paradigms and the multifaceted dimensions of human queries. Inspired by the capabilities of Retrieval Augmented Generation (RAG), this project goes a step further by employing multiple query generation and Reciprocal Rank Fusion to re-rank search results.  </p>


<div style="margin: 20px 0;">
  <img src="./assets/RAG-Fusion1.png" width="1747" height="600"  style="border-radius: 20px; box-shadow: 0 8px 32px rgba(0, 217, 255, 0.3);">
  
</div>


---

### [Answer recursively](LocalRAG_Answer_recursively_LLama3_Nvidia_Stocks.ipynb)
<p align="justify"> 
The recursive RAG method, exemplified by Interleaving Retrieval with Chain-of-Thought (IRCoT), is an advanced approach for solving complex, multi-step questions. Unlike standard Retrieval-Augmented Generation (RAG), which performs a single initial document retrieval, this technique interleaves the reasoning and retrieval processes iteratively. It starts by using the question to retrieve initial context and generate the first logical step of an answer. Crucially, this intermediate thought or partial conclusion is then treated as a new, refined query to guide the next retrieval. This recursive loop—Reason 
→
 Retrieve 
→
 Reason—continues, with each step building upon the knowledge gained in the previous cycle. This process allows the Large Language Model to acquire increasingly specific, targeted information as it progresses, ensuring that its ongoing reasoning is continuously grounded by up-to-date, externally retrieved evidence, thereby significantly boosting accuracy on knowledge-intensive, compositional queries and mitigating factual errors (hallucination).  </p>


<div style="margin: 20px 0;">
  <img src="./assets/Answer recursively2.png" width="1747" height="600"  style="border-radius: 20px; box-shadow: 0 8px 32px rgba(0, 217, 255, 0.3);">
  
</div>




---

### [Answer individually](LocalRAG_Answer_individually_LLama3_Nvidia_Stocks.ipynb)
<p align="justify"> 
An advanced method for information retrieval and question answering called the Answer Individually .In this method, a main Question is broken down into multiple sub-questions (Q1, Q2, Q3). Each sub-question independently uses a Vectorstore to retrieve relevant Documents. Subsequently, a Large Language Model processes each set of retrieved documents to generate an Answer for that specific sub-question. Finally, all the individual answers generated for the sub-questions are combined and processed again by a final LLM to provide a comprehensive and final Answer to the original main question. This approach allows the model to better handle the complexities of multi-faceted questions and deliver more accurate and complete responses.  </p>


<div style="margin: 20px 0;">
  <img src="./assets/Answer individually1.png" width="1747" height="600"  style="border-radius: 20px; box-shadow: 0 8px 32px rgba(0, 217, 255, 0.3);">
  
</div>



---

### [Hypothetical Document Embeddings (HyDE)](LocalRAG_HyDE_LLama3_Nvidia_Stocks.ipynb)
<p align="justify"> 
The Hypothetical Document Embeddings (HyDE) method is a fully zero-shot dense retrieval approach that avoids the need for relevance labels by pivoting through a generated, hypothetical document. Given a query, HyDE first uses an instruction-following language model (like InstructGPT) to generate a hypothetical document that captures relevance patterns related to the query, even though it may be factually incorrect or "unreal". Then, an unsupervised contrastive encoder (like Contriever) encodes this generated document into an embedding vector. This vector is used to identify a neighborhood in the corpus embedding space, allowing the retrieval of similar real documents based on vector similarity, with the encoder's dense bottleneck serving to filter out the incorrect details of the hypothetical document. This process casts the retrieval task into a generative task and a document-document similarity task, without explicitly modeling or computing a query-document similarity score.  </p>


<div style="margin: 20px 0;">
  <img src="./assets/HyDE.png" width="1747" height="500"  style="border-radius: 20px; box-shadow: 0 8px 32px rgba(0, 217, 255, 0.3);">
  
</div>


---

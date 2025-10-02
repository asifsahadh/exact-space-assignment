
-----------------
DESIGN TRADE-OFFS
-----------------
1. In the prompt for the VLM that describes the image, we provide the text surrounding the image as further context for it to potentially describe the image with better accuracy. However, this is not foolproof. Sometimes some context may be given in the next page. Sometimes the figure label alone may be sufficient for describing the image. These are not precisely taken care off.
2. The local VLM takes a very long time to process each image. For this reason, currently only the initial 30 pages is used for images processing. This alone took 7.7 hours. 

------------------
RETRIEVAL STRATEGY
------------------
The chunks are converted to vector embeddings using sentence transformer, which is able to ultimately capture contextual relationships between words and is not just a keyword based embedding model.
The user query is passed into the same embedding model and using cosine similarity, the top-k chunks indices are retrieved. This is reranked and passed into the final LLM for answer generation.

----------
GUARDRAILS
----------
1. In the prompts, it has been mentioned to not make up answers and not to hallucinate. If the LLM does not know the answer, it must simply respond by mentioning that it doesn't know.
2. For the final answer, the LLM is asked to provide the reference (page number) from where the information is taken. In the data engineering pipeline, the page number is added as metadata, which can be ultimately utilized by the final LLM for this purpose. 

------------
SCALING PLAN
------------
1. Efficiency wise, it is possible that scaling with regards to multiplying the number of documents won't cause an issue. Accuracy wise, based on my testing, did not cause an issue as well. My initial test involved only a 4 paged document, and it was able to answer my queries accurately by providing references. After scaling to all the document (196 pages), the same query was still being answered the same way.
2. If the users have a GPU based PC, then they can use this system locally. Since the RAG will run on edge, user scaling is not a problem.
3. The best way to deploy this under cost-constraints is to make most of the functions run locally. This means we might have to use heavily quantized open source locally deployable models, but at the cost of accuracy. Another obvious way is to use cloud based models that are cheap. This will require studying multiple models and evaluating them.
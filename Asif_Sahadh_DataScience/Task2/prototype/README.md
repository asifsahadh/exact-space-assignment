
---------
RUN STEPS
---------

1. Primarily, make sure to run the requirements.txt file in a fresh environment:
    pip install -r requirements.txt
2. After importing the libraries, directly jump to "RAG Setup" section. The cells before this section and after importing of libraries are for data engineering and getting all the data from the PDF file. 
3. A file named 'data_array' exists inside prototype. This is the data array acquired after extracting all the information from the PDF. The "RAG Setup" section starts by loading this file.
4. After this, everything can be run sequentially until the end.
5. In order to change the user query, there is a variable names 'QUERY'. For my testing, I had given the query "Tell me about kice cyclone parts.". This may be changed and after changing, make sure to run all the cells below including it. The final cell at the "Inference" section is where you can see the output to the query.

Note: Due to time constraints, I was not able to make a proper runnable function where you simply need to pass the query to get the final output. Also for the same reason, and also due to lack of proper knowledge on LLM evaluation, I was not able to implement LLM evaluation strategies.

--------------------------------------------
FREE / OPEN MODELS TO DOWNLOAD & RUN LOCALLY
--------------------------------------------

For image processing, I used Ollama model gemma3:4b-it-qat. This has to be installed locally via Ollama. For other tasks, I sourced the gpt-oss-120b model from Groq Cloud. Their documentation provides information on how to use their models for inference. You will have to make an account and get hold of an API key to use their models.

    Ollama: https://ollama.com/
    Groq Cloud: https://console.groq.com/home
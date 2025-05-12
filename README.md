[0:00 – 0:30] – Introduction
"Hi, I’m Sarvesh Shukla, and in this 4-minute walkthrough, I’ll demonstrate a project where I built a Retrieval-Augmented Generation system using Google’s Gemini API.

The goal of the task was to design a system that could take a user’s query, search the internet for relevant information, process that data, and generate a smart, contextual response using a Large Language Model.

I enhanced the given starter code, completed all missing parts, and made critical updates to ensure it is production-ready."

⏱️ [0:30 – 1:15] – High-Level Architecture
(Switch to diagram or folder view briefly while explaining)

"The system architecture consists of:

A Streamlit-based front-end where users enter queries.

A Flask backend API that processes the query, fetches articles, and generates a response.

Serper API to search the internet.

Gemini 1.5 Flash as the LLM engine.

And a conversational memory mechanism for context-aware answers.

Now let me walk you through the main files and the exact changes I made."

⏱️ [1:15 – 2:30] – Key File Changes
🔁 utils.py — Core Logic
"In utils.py, I made the following major updates:

Integrated Gemini 1.5 Flash using google-generativeai. I removed OpenAI dependencies and configured Gemini using environment variables.

Added conversational memory using a dictionary that stores user queries and responses. This helps the model generate more contextually relevant answers.

Implemented full logic for search_articles() using the Serper API to fetch top articles.

Completed fetch_article_content() using BeautifulSoup to extract headings and paragraphs while filtering noise.

In generate_answer(), I appended previous conversation history and content into the prompt before calling Gemini, ensuring more natural responses."

🧠 app.py (Flask) — Backend Pipeline
"In the Flask app.py file:

I connected the /query endpoint to all utility functions.

Implemented the entire control flow: receive query → search articles → fetch & clean content → pass to Gemini → return the answer.

Used jsonify to return proper JSON responses.

Ensured error handling for missing queries or empty article results.

Integrated the user_id field to support per-user memory."

💻 app.py (Streamlit) — Front-End Improvements
"In the Streamlit front-end:

I added a clean and intuitive user interface with titles, icons, and a placeholder.

Connected the frontend to the Flask backend via POST requests.

Added a spinner for better UX while waiting.

Displayed responses using markdown() and handled backend failures gracefully.

Ensured that the returned key from the Flask backend matched with response['response'].

This creates a smooth interaction loop from query input to LLM response."

⏱️ [2:30 – 3:10] – Environment & Dependencies
"I also updated the requirements.txt file to remove OpenAI and include only relevant packages:

txt
Copy
Edit
flask
streamlit
requests
beautifulsoup4
python-dotenv
google-generativeai==0.4.1
I used a .env file to securely manage API keys for Serper and Gemini."

⏱️ [3:10 – 3:40] – Live Demonstration (as you perform it)
"Now let’s test it in real-time. I’ll enter a query like: “What is quantum computing?”

You can see the system fetches relevant articles, processes them, and returns an intelligent answer from Gemini — all within a few seconds.

The model also remembers previous queries if I continue the conversation, thanks to the memory layer."

⏱️ [3:40 – 4:00] – Conclusion & Job Fit
"This project demonstrates my ability to:

Build full-stack AI systems

Integrate APIs like Serper and Gemini

Handle real-world web scraping and NLP tasks

Design modular, production-ready codebases

I’m passionate about building intelligent applications that solve real problems, and I’m confident that I can bring this level of initiative and precision to your team. Thank you!"

✅ Tips for Recording
Keep your tone confident, clear, and conversational.

Use your actual screen to show:

Folder structure

Code highlights (not the entire file)

Live test in Streamlit

Avoid rushing — aim for a calm 4-minute delivery.

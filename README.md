# Movie Recommendation System using LLMs

This project presents an advanced approach to movie recommendation by integrating LLM-based genre prediction, script summarization, and user interaction data. It leverages YouTube trailer transcriptions, Whisper ASR, and the LLAMA 3.1 8B-instant model via Langchain’s ChatGroq to build a personalized movie ranking system.

---

## Project Overview

Traditional recommendation systems depend heavily on numerical ratings and basic metadata. This project enhances such systems by incorporating natural language understanding of movie scripts and the reasoning capabilities of large language models to generate context-aware and personalized recommendations.

---

## Key Features

- **Script Extraction**  
  Transcripts were obtained from YouTube trailers using:
  - YouTube Transcript API  
  - Whisper ASR for trailers without transcripts

- **Summary Generation**  
  Summaries were generated from transcribed scripts using LLAMA 3.1 8B-instant, enabling a content-aware basis for recommendations.

- **Genre Prediction**  
  LLAMA was prompted to predict movie genres based on the generated summaries. These predicted genres enhance metadata for improved personalization.

- **User Interaction-Based Prompting**  
  - Each user is associated with 20 movies, ranked from most to least liked  
  - The first 15 movies (with summaries and predicted genres) are given to the model  
  - The model is prompted to predict the ranking order of the remaining 5 movies as a Python list

- **Ranking Task**  
  The predicted rankings are compared with actual user preferences to evaluate recommendation quality.

---

## LLM Usage

- **Model**: LLAMA 3.1 8B-instant  
- **Platform**: Langchain + ChatGroq  
- Prompts are crafted to simulate human reasoning in predicting genres and understanding user preferences based on plot summaries.

---

## Evaluation

- **Summary Quality**  
  Evaluated using ROUGE metrics:
  - ROUGE-1
  - ROUGE-2
  - ROUGE-L

- **Genre Classification**  
  Measured using:
  - Precision  
  - Recall  
  - F1 Score (per genre)

- **Recommendation Performance**  
  Evaluated using:
  - Precision@k  
  - NDCG (Normalized Discounted Cumulative Gain)

---

## Datasets

- **User Interaction Data**  
  MovieLens 100k dataset  
  - 943 users  
  - 1,600 movies  
  - Ratings range from 1 to 5

- **Fallback Handling**  
  If a trailer summary was unavailable, LLAMA generated the summary using model knowledge.

---

## Applications

- Personalized movie recommendation engines  
- Content-aware streaming services  
- LLM-driven multimedia understanding and analytics

---

## Future Enhancements

- Incorporate fine-tuned LLMs specifically trained on movie plots  
- Integrate user demographics and contextual data  
- Add real-time feedback loops to continuously improve recommendation quality

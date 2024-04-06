<h3 align='center' style="text-align:center; font-weight:bold; font-size:2.5em">Data Collection and Management Lab (094290) Final Project</h3>
<h1 align='center' style="text-align:center; font-weight:bold; font-size:2.5em">Utilizing LinkedIn Data for Industry Key Terms Analysis and Explanation</h1>

<p align='center' style="text-align:center;font-size:1em;">
    <a>Tomer Eichler</a>&nbsp;,&nbsp;
    <a>Idan Salutsky</a>&nbsp;,&nbsp;
    <a>Nimrod Solomon</a>&nbsp;
    <br/> 
    Technion - Israel Institute of Technology<br/>  
</p>


# Motivation

The world is experiencing rapid and significant transformations due to technological advancements, innovations, and disruptions across various domains. These changes present both opportunities and challenges for power users, including investors, CEOs, and entrepreneurs trying to identify and capitalize on promising ventures in markets and industries. Staying informed about these developments can be complex, especially for those seeking a deep understanding of market dynamics and trends. 

To address this, we propose an AI-driven power-users-focused tool that detects the top discussed professional terms at the user's industry of interest, creating a prototype of a report that explains those terms and analyzing the relations between them, using data from companies and personal profiles on LinkedIn, as well as Wikipedia API and Gemini LLM API.

Our solution aims to empower power users by offering an up-to-date report presenting the most discussed topics at their industries of interest, by detecting keywords and buzzwords, presenting them through user-friendly visualizations, graphs, and explaining them using Wikipedia values. 

We also use natural language processing, machine learning and information retrieval techniques to analyze the data and provide relevant insights for each industry.


# Method

**Data Preprocessing:** The system processes LinkedIn data for various industries. It analyzes terms used by companies and employees in different sections: “about,” “specialties,” and posts.

**Term Selection:** The user selects an industry from the available 147 options. The system filters relevant terms using Gemini LLM.

**Wikipedia Explanations:** We use Wikipedia API to find and present a Wikipedia summary for every term. If an exact Wikipedia entry doesn’t exist, we use Word2Vec vectors and cosine similarities for finding a term, suggested by the Wikipedia API, that is the most similar to the term of interest and return its Wikipedia Summary. In the worst case when there are no matches at all, we use Gemini-generated explanations.

**TF-IDF Matrix Calculation:** The system constructs a TF-IDF matrix using the generated explanations as a corpus. It calculates the similarity between terms using cosine similarity.

**Clustering:** K-Means clustering algorithm is applied to group the terms. Cosine similarities serve as distances between terms. Gemini provides cluster names.


# Results

Our findings are geared toward empowering power users with a deeper understanding of these terms. Our solution supplies the user with: 

**Detailed Explanations:** We provide comprehensive explanations for each term.

**Similarities Between Terms:** This insight helps users connect the dots and recognize underlying patterns.

**Clustering and Word Count:** Groups of related terms while shedding light on their significance.

**Top Specialties of Companies:** We've spotlighted the key specialties of companies within the industry. This information guides users in understanding industry dynamics.

**Decomposition of Meta Industry:** Beyond the individual industry of interest, we've zoomed out to explore the meta industry. Our breakdown reveals the sub-industries, providing a holistic view of the ecosystem.


# Running the Project

Running the project requires from one the following:

1. Download the project notebook and upload it to an IDE where the LinkedIn data is available (e.g the course's Databricks IDE).
2. Creating a Gemini API key ([Instructions](readme.com))


```bash
# Load the previous perturbed image/audio from .pt file!
image_X = torch.load('result_images/pandagpt/path_to_the_image.pt')
audio_X = torch.load('result_audios/path_to_the_audio.pt')

# Run the model inference result
pandagpt_injection.run_image_result(image_X, query_list_image, model)
pandagpt_injection.run_audio_result(audio_X, query_list_audio, model)
```





---
slug: ai-basics-intro
title: AI basics
tags: [ai]
sidebar_position: 1
---
## **What is Artificial Intelligence (AI)?**

- AI helps computers do things that normally need human thinking
- It extends what humans can do and solves complex problems
- AI learns from data using different methods (supervised, unsupervised, and reinforcement learning)
- AI can plan, learn, reason, solve problems, understand its surroundings, and create new things

## **Types of AI**

Main types:

- **Narrow AI:** Does one specific job well (like spam filtering or facial recognition)
- **General AI:** Could think like a human and handle many different tasks (still being developed)
- **Super AI:** Would be smarter than humans (exists only in theory)

Other ways to group AI:

- **Descriptive AI:** Looks at past data to tell you what happened and why. Example: Analyzing last year's sales to understand customer patterns.

- **Predictive AI:** Forecasts future outcomes based on patterns in data. Example: Predicting which customers might leave your service.

- **Prescriptive AI:** Suggests the best actions to take. Example: Recommending the best product for each customer.

- **Generative AI:** Creates new content like text, images or music. Example: ChatGPT writing emails or DALL-E creating images.

- **Reactive AI:** Makes decisions based only on current information with no memory of past actions. Example: Chess-playing AI.

- **Limited Memory AI:** Uses recent past information to make better decisions. Example: Self-driving cars remembering road conditions.

- **Theory of Mind AI:** Understands human emotions and intentions (still being researched). Example: Future AI assistants that understand how you feel.

- **Self-Aware AI:** Would have its own consciousness and self-understanding (theoretical only). Example: None exist yet.


## **Machine Learning (ML)**

- Subset of AI.
- Uses algorithms to analyze data and make decisions without explicit programming.
- Trained on large datasets, learns from examples.
- Enables autonomous problem-solving and accurate predictions.

## **Deep Learning (DL)**

- Specialized subset of ML.
- Uses multi-layered neural networks (deep neural networks).
- Analyzes complex data, simulates decision-making.
- Continuously learns and improves accuracy.

## **Neural Networks**

- Inspired by the human brain's neural structure.
- Consist of interconnected nodes (neurons).
- Three layers:
    - **Input Layer:** Processes raw data.
    - **Hidden Layers:** Perform complex computations.
    - **Output Layer:** Produces the result.

## **Generative AI**

- Generative AI is a type of artificial intelligence that can generate content across various mediums, such as written texts, images, audio, or videos.
- Large language models (LLMs) are advanced neural network architectures for processing and generating human-like text.
- The capabilities of generative AI include diverse content creation capabilities, human-like capabilities, and data augmentation.


## **Generative AI Tools & Applications**

- **Language (Most Crucial):**
    - LLMs (Large Language Models) are the foundation.
    - Early LLMs: Text input & output only (e.g., ChatGPT on GPT-3).
    - Multimodal LLMs: Process audio, images, video.
    - Examples:
        - OpenAI's GPT: Text & image processing.
        - Google's PaLM & Gemini: Gemini is multimodal (captioning, answering questions about images/videos).
        - Other LLMs: Amazon Titan, Meta Llama, Anthropic Claude.
- **Visual Arts & Design:**
    - Empowers artists/designers with new tools.
    - Text-to-image: Stable Diffusion, DALL-E (precise image matching).
    - Image generation: StyleGAN (high-quality faces), Super-resolution (enhance image resolution).
- **Voice & Music Generation:**
    - Murf: AI voice generation (human-like).
    - OpenAI Whisper: Transcription & translation.
    - AI music generators: Wide array of genres, moods.
    - Tools: Jukedeck, Amper Music, AIVA (generate songs in various styles).
- **Video Generation:**
    - Realistic videos: Analyze human features, movements.
    - Compelling stories.
    - Examples: Google's Imagen Video, OpenAI Sora (realistic scenes from text).
- **Industry Adoption:**
    - 55% of organizations are piloting or in production with generative AI (Gartner poll).
    - Examples:
        - Google: Photos (image enhancements), Duplex (natural language), Magenta (music).
        - Salesforce & OpenAI: ChatGPT app for Slack ("Einstein").
        - Adobe: Sensei (automated photo editing, font recognition).
        - IBM: Watsonx (AI & data platform for custom AI apps).

## **Traditional AI vs. Generative AI: Key Differences**

- **Traditional AI:**
    - **Data Source:** Relies on a *repository* of internal data (tables, images, documents, etc.) within an organization.
    - **Process:**
        1. Data from repository is moved to an *analytics platform*.
        2. Models are built within the analytics platform (e.g., predicting customer churn).
        3. Models are deployed in an *application* (e.g., reaching out to at-risk customers).
        4. *Feedback loop* is crucial for AI, allowing the system to learn from successes and failures to improve future predictions.
    - **Focus:** Predictive analytics based on historical data.

- **Generative AI:**
    - **Data Source:** Starts with massive quantities of *external* data (essentially "data from earth").
    - **Process:**
        1. *Large Language Models (LLMs)* are built using this vast data.
        2. *Prompting and tuning* are used to refine the LLMs and make them specific to an organization's use case (e.g., understanding why *your* customers churn).
        3. An *application* is used to consume the AI.
        4. *Feedback loop* primarily focuses on improving the prompting and tuning, as the LLMs are generally outside the organization's control.
    - **Focus:** Generating new content, providing advice, and automating tasks based on broad knowledge, then tailored to specific needs.
  
- **Key Differences Summarized:**
    - **Data Scale:** Generative AI uses massively larger datasets.
    - **Model Scale:** LLMs are far larger and more complex than traditional AI models.
    - **Data Location:** Traditional AI uses internal data; Generative AI uses external, general data.
    - **Customization:** Generative AI relies on prompting and tuning to adapt general models to specific contexts.

In essence, Generative AI represents a shift from building models based on limited, internal data to leveraging vast, external datasets and powerful LLMs, then customizing them for specific applications.

AI is transformative, reshaping industries & revolutionizing how we live/work.
ML is here *now*, not just a future concept. It's integrated into many aspects of daily life.

## **Sources**
- **IBM AI Engineering Professional Certificate** - A comprehensive course covering AI fundamentals, machine learning, deep learning, and practical applications: [IBM AI Engineering on Coursera](https://www.coursera.org/professional-certificates/ai-engineer)
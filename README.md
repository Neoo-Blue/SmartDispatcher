Smart Dispatcher: AI Task Router
Overview
Smart Dispatcher is a Python-based tool designed to automatically route and execute AI tasks using the most appropriate model from various providers. It prioritizes reliability, with features like failover mechanisms, greeting rules, expanded query categories, token/difficulty-aware model selection, robust JSON parsing for classification, and prevention of duplicate headers in responses.
Built with a focus on efficiency and fault tolerance, it classifies user queries (e.g., by topic like "chat," "coding," or "news") and dispatches them to models from OpenAI, Google Gemini, xAI Grok, or Perplexity Sonar. This ensures optimal performance while handling errors gracefully.
Key Features

Intelligent Classification: Uses a configurable AI model (default: Google Gemini) to categorize queries by topic, difficulty (easy/medium/hard), and token needs (low/medium/high).
Model Routing: Maps categories to specialized models, with adjustments for query complexity (e.g., smaller variants for simple tasks).
Failover Support: Automatically switches to alternate models on API errors, rate limits, or invalid outputs, preferring different providers with similar specialties.
Greeting Optimization: Rule-based handling for simple greetings to skip classification and use fast, low-cost models.
Expanded Categories: Supports over 40 topics, including emotion, profanity, coding, news_analysis, ai_ethics, finance, devops, and general catch-alls.
Robust Parsing: Handles classifier outputs with JSON loading, regex fallback, and ast.literal_eval for reliability.
Duplicate Prevention: Avoids repeating selection banners in multi-turn conversations.
Configurable Valves: Pydantic-based settings for API keys, allowed/disabled models, classifier choice, and display options (e.g., show reasoning).
Supported Models:

OpenAI: GPT-3.5-Turbo, GPT-4, GPT-4o, GPT-4o-Mini, ChatGPT-4o-Latest (plus demonstrative GPT-5 variants).
Google Gemini: 2.5-Flash (fast/general), 2.5-Pro (advanced/reasoning/multimodal).
xAI Grok: Grok-3, Grok-3-Fast, Grok-4-0709 (with vision/tool use).
Perplexity Sonar: Standard, Pro, Reasoning, Deep-Research variants for search-grounded answers.


Execution Modes: Option to simulate (without executing) or fully run tasks with selected models.

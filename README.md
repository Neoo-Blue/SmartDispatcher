# Smart Dispatcher: AI Task Router 🤖

[![Python Version](https://img.shields.io/badge/python-3.9+-blue.svg)](https://www.python.org/downloads/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Build Status](https://img.shields.io/badge/build-passing-brightgreen)](https://github.com/)

Smart Dispatcher is a Python-based tool designed to automatically route and execute AI tasks using the most appropriate model from various providers. It prioritizes reliability and efficiency by classifying user queries and dispatching them to the best-suited model from providers like OpenAI, Google, xAI, or Perplexity.

Built with a focus on fault tolerance, it incorporates features like failover mechanisms, greeting-handling rules, expanded query categories, and robust JSON parsing to ensure optimal performance while handling errors gracefully.

---

## Key Features ✨

* **Intelligent Classification**: Uses a configurable AI model (default: `Google Gemini`) to categorize queries by topic, difficulty (`easy`/`medium`/`hard`), and token needs (`low`/`medium`/`high`).
* **Dynamic Model Routing**: Maps categories to specialized models, with automatic adjustments for query complexity. For example, it routes simple tasks to smaller, faster model variants.
* **Advanced Failover Support**: Automatically switches to alternate models in case of API errors, rate limits, or invalid outputs. It intelligently prefers models from different providers with similar specialties to maximize uptime.
* **Greeting Optimization**: Implements rule-based handling for simple greetings (e.g., "hello," "thank you") to bypass the classification step and use fast, low-cost models directly.
* **Expanded Categories**: Supports over 40 topics, including specialized areas like `emotion`, `profanity`, `coding`, `news_analysis`, `ai_ethics`, `finance`, and `devops`, plus general catch-alls.
* **Robust Parsing**: Reliably handles classifier outputs by attempting JSON loading first, with fallbacks to regex extraction and `ast.literal_eval` to ensure system stability.
* **Duplicate Prevention**: Prevents the repetition of selection banners and reasoning in multi-turn conversations for a cleaner user experience.
* **Configurable Valves**: Leverages Pydantic for settings management, allowing easy configuration of API keys, enabled/disabled models, classifier choice, and display options (e.g., showing classification reasoning).
* **Execution Modes**: Offers two modes: **simulate** (shows which model would be chosen without running the task) and **run** (fully executes the task with the selected model).

---

## Supported Models 🧠

The dispatcher supports a wide range of models from leading providers:

* **OpenAI**:
    * `GPT-3.5-Turbo`
    * `GPT-4`
    * `GPT-4o`
    * `GPT-4o-Mini`
* **Google Gemini**:
    * `2.5-Flash` (Optimized for speed and general tasks)
    * `2.5-Pro` (Designed for advanced reasoning and multimodal inputs)
* **xAI Grok**:
    * `Grok-3` & `Grok-3-Fast`
    * `Grok-4-0709` (Includes vision and tool use capabilities)
* **Perplexity Sonar**:
    * `Standard`, `Pro`, `Reasoning`, and `Deep-Research` variants for search-grounded, accurate answers.

---

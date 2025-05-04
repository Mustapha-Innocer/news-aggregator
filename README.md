# 📰 LLM News Aggregation System

A microservice-based system that scrapes news stories from various websites, uses large language models (LLMs) to summarize and categorize them, stores them in a database, and makes them accessible via a RESTful API for rendering on a user interface.

## 🔧 Architecture Overview

This project follows a **microservices architecture**, with each component handling a specific part of the news processing pipeline. Communication between services is handled using **Apache Kafka**.

![System Architecture](./assets/system_architecture.svg)

### 🚀 Services Breakdown

1. **🕷️ Scraping Service**
   - Scrapes news stories from multiple online sources.
   - Publishes raw news data to a Kafka topic.

   👉 [Scraper Service Repository](https://github.com/Mustapha-Innocer/scraping-service)

2. **🧠 LLM Service**
   - Subscribes to the raw news topic.
   - Summarizes and categorizes each article using LLMs.
   - Publishes processed stories to another Kafka topic.

   👉 [LLM Processor Service Repository](https://github.com/Mustapha-Innocer/llm-service)

3. **💾 Storage Service**
   - Consumes summarized news from the LLM service.
   - Stores categorized and summarized stories into a structured database.

   👉 [Storage Service Repository](https://github.com/Mustapha-Innocer/storage-service)

4. **🌐 API Service**
   - Exposes RESTful endpoints to retrieve categorized news from the database.
   - Designed for integration with frontend interfaces.

   👉 [API Service Repository](https://github.com/Mustapha-Innocer/api-service)

## 🧱 Tech Stack

- **Python** (FastAPI, BeautifulSoup, Asycio, etc)
- **Kafka** for inter-service messaging
- **PostgreSQL** for storage
- **LLM Integration** (HuggingFace)
- **Redis** for caching processed news stories

## 📦 Deployment

Each service is containerized with Docker and can be deployed using Docker Compose or Kubernetes.

## 📄 License

This project is licensed under the MIT License.

---

Made with ❤️ by [Mustapha Innocer](https://github.com/Mustapha-Innocer)

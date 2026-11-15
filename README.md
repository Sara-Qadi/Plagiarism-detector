# Real-time plagiarism detection

A big data course project (Dec 2025 – Feb 2026) that finds copied work across a large stream of student submissions as they arrive. It processed 24,000+ submissions in real time with Apache Kafka and Spark Structured Streaming in Scala.

Exact and near duplicates are found with MinHash LSH and cosine similarity from Spark MLlib. Results are stored in MongoDB, and the whole system starts with Docker Compose.

## How the pieces fit

Submissions → producer → Kafka → preprocessing → MinHash LSH + cosine similarity → MongoDB

Each step lives in its own repository:

| Repository | What it does |
|---|---|
| [Plagiarism-infrastructure](https://github.com/Sara-Qadi/Plagiarism-infrastructure) | Docker Compose file that starts Kafka, Spark and MongoDB |
| [Plagiarism-producer](https://github.com/Sara-Qadi/Plagiarism-producer) | Streams submissions into Kafka |
| [Plagiarism-consumer](https://github.com/Sara-Qadi/Plagiarism-consumer) | Kafka consumer that reads the stream |
| [Plagiarism-preprocessing](https://github.com/Sara-Qadi/Plagiarism-preprocessing) | Cleans and normalizes the text |
| [Plagiarism-minhash](https://github.com/Sara-Qadi/Plagiarism-minhash) | Finds near duplicates with MinHash LSH |
| [Plagiarism-cosine-similarity](https://github.com/Sara-Qadi/Plagiarism-cosine-similarity) | Scores similarity between submissions |
| [Plagiarism-mongodb](https://github.com/Sara-Qadi/Plagiarism-mongodb) | Saves results to MongoDB |

## Stack

Scala, Apache Kafka, Spark Structured Streaming, Spark MLlib, MongoDB, React, Docker Compose.

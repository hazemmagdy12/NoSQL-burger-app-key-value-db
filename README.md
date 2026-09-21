# 🛒 Burger App: Key-Value Database (Phase 2 of NoSQL Series)

## 📌 Project Overview
This repository is the second phase of my Data Engineering portfolio series demonstrating **Polyglot Persistence**. 

This project focuses on **Key-Value NoSQL Databases** using Redis. It is designed to act as a high-speed, in-memory buffer to handle real-time user sessions and shopping cart operations. By using Redis Hashes and TTL (Time-To-Live), the system ensures ultra-low latency while preventing database bloat from abandoned carts.

## 🗺️ The Polyglot Data Ecosystem Roadmap
1. 🟢 **Phase 1: Document DB** (Astra DB for core catalog and menus).
2. 🟢 **Phase 2: Key-Value DB** (This Repo - Redis for shopping carts and sessions).
3. ⏳ **Phase 3: Wide-Column DB** (Cassandra for user activity tracking).
4. ⏳ **Phase 4: Graph DB** (Neo4j for AI recommendation engine).
5. ⏳ **Phase 5: The Integrator** (Orchestrating the databases together).

## 🏗️ Project Architecture (Clean Code Design)
The application logic is decoupled into specific modules:
* `db_connection.py`: Establishes a secure connection to the Redis Cloud instance using environment variables.
* `cart_services.py`: Contains the core business logic using Redis Hashes (`HINCRBY`, `HGETALL`, `HDEL`) to manage cart items and sets auto-expiration (`EXPIRE`) for memory management.

## 🛠️ Tech Stack
* **Database:** Redis Cloud (In-Memory Key-Value Data Store)
* **Language:** Python 3
* **Libraries:** `redis`, `python-dotenv`

## 🚀 Setup & Installation
1. Clone the repository and navigate to the directory:
   ```bash
   git clone [https://github.com/hazemmagdy12/NoSQL_burger-app-key-value-db.git](https://github.com/hazemmagdy12/NoSQL_burger-app-key-value-db.git)
   cd NoSQL_burger-app-key-value-db

python -m venv venv
source venv/Scripts/activate  # On Windows

pip install -r requirements.txt

REDIS_HOST="your_redis_host_endpoint"
REDIS_PORT="your_redis_port"
REDIS_PASSWORD="your_redis_password"

python cart_services.py
   

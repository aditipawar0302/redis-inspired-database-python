# Redis-Inspired In-Memory Database Server

A miniature Redis-like in-memory key-value database server implemented in Python.

## Overview

This project demonstrates how a basic database server works using Python, TCP socket communication, and a client-server architecture.

The server stores data in memory as key-value pairs and provides a Python client for interacting with the database.

## Features

- In-memory key-value storage
- TCP socket-based client-server communication
- Python client interface
- Redis-inspired database commands
- Multiple-key operations
- Support for strings, numbers, lists, dictionaries, and NULL values
- Concurrent client handling using gevent or threads
- Unit testing
- Docker support
- GitHub Actions workflow

## Supported Commands

| Command | Description |
|---------|-------------|
| `SET` | Store a value using a key |
| `GET` | Retrieve a value using a key |
| `DELETE` | Delete a key |
| `MGET` | Retrieve multiple values |
| `MSET` | Store multiple key-value pairs |
| `FLUSH` | Remove stored data |

## Technologies

- Python
- TCP/IP
- Socket Programming
- Client-Server Architecture
- Key-Value Database
- Serialization / Deserialization
- Gevent
- Unit Testing
- Docker
- GitHub Actions

## Installation

Clone the repository:

```bash

Create a virtual environment:
python -m venv .venv
.\.venv\Scripts\Activate.ps1

Install dependencies:
pip install -r requirements.txt

Running the Server
Start the database server:
python simpledb.py

The default server runs on:
127.0.0.1:31337

Using the Client
Open another terminal and run:
from simpledb import Clientclient = Client()client.set("name", "Aditi")print(client.get("name"))


Output:
Aditi

Multiple Values
client.mset({    "name": "Aditi",    "city": "Pune",    "role": "Software Engineer"})print(client.mget("name", "city", "role"))


Output:
['Aditi', 'Pune', 'Software Engineer']

Delete
client.delete("name")


Flush
client.flush()


Running Tests
Run the test suite:
python tests.py

The project also includes a GitHub Actions workflow for automated testing.
Docker
Build the Docker image:
docker build -t redis-inspired-database ./docker

Run the container:
docker run -p 31337:31337 redis-inspired-database

Architecture
Python Client
      |
      | TCP Socket
      v
Database Server
      |
      v
Command / Protocol Handler
      |
      v
In-Memory Key-Value Store
git clone https://github.com/aditipawar0302/redis-inspired-database-python.git
cd redis-inspired-database-python

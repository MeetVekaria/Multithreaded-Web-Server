# Multithreaded Web Server

A minimal **plain-Java** project demonstrating three simple server implementations (no frameworks):

- **Single-threaded** — processes one connection at a time  
- **Multithreaded** — spawns a new `Thread` per connection  
- **ThreadPool** — uses a fixed-size `ExecutorService` worker pool

This repo is educational — focused on sockets, threading, and basic request/response behavior.

---

## Repository layout

Multithreaded-Web-Server/
├─ SingleThreaded/ # Server.java, Client.java (single-threaded)
├─ Multithreaded/ # Server.java, Client.java (one-thread-per-connection)
├─ ThreadPool/ # Server.java (thread-pool implementation)
└─ README.md


---

## Build & Run

Run these commands from the repository root. Adjust paths or ports if your files are in different locations.

```bash
# clone if needed
git clone https://github.com/MeetVekaria/Multithreaded-Web-Server.git
cd Multithreaded-Web-Server

# Compile the implementations (no packages assumed)
javac -d out/SingleThreaded SingleThreaded/*.java
javac -d out/Multithreaded Multithreaded/*.java
javac -d out/ThreadPool ThreadPool/*.java

# Run a server (example: ThreadPool server on port 8010)
# Replace the class name with the correct one if different; here the main classes are named `Server`.
java -cp out/ThreadPool Server 8010

# In other terminal(s) run clients that connect to the server
# For the multithreaded client example (spawns many clients):
java -cp out/Multithreaded Client

# For the single-threaded client (single connection):
java -cp out/SingleThreaded Client

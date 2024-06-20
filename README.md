# Multithreaded Proxy Server

## Introduction
The Multithreaded Proxy Server is designed to handle multiple client requests simultaneously, providing a practical understanding of how requests from a local computer are processed and sent to a server. It also explores the implementation of multithreading, cache management, and concurrency control.

## Basic Working Flow of the Proxy Server
- Client sends a request to the proxy server.
- Proxy server processes the request and forwards it to the destination server.
- The destination server responds back to the proxy server.
- Proxy server sends the response back to the client.

## Multi-threading Implementation
To implement multithreading, we used Semaphores instead of Condition Variables along with `pthread_join()` and `pthread_exit()` functions:
- **Semaphores**: Semaphores are preferred over `pthread_join()` as they do not require passing the thread ID to wait for. `sem_wait()` and `sem_post()` functions are used for synchronization.
- **Threading**: Each client request is handled by a separate thread, improving efficiency and response time.

## Motivation/Need for the Project
The project aims to:
- Understand the process of sending requests from a local computer to a server.
- Handle multiple client requests concurrently.
- Implement concurrency control through locking mechanisms.
- Explore caching mechanisms and their use in web browsers.

## Proxy Server Functions
- **Speed**: Enhances the speed of processing requests and reduces server traffic.
- **Restriction**: Can restrict user access to specific websites.
- **Anonymity**: Changes the IP address to keep the client's identity hidden from the server.
- **Security**: Can be modified to encrypt requests, preventing unauthorized access.

## OS Components Used
- **Threading**: For handling multiple client requests simultaneously.
- **Locks**: To manage concurrent access to shared resources.
- **Semaphore**: For synchronization between threads.
- **Cache**: Utilizes the LRU (Least Recently Used) algorithm for efficient caching.

## Limitations
- **Multiple Clients**: If a URL opens multiple clients, each response is stored separately, leading to partial responses during cache retrieval.
- **Cache Size**: Fixed cache element size limits the storage of large websites.

## Future Enhancements
- **Multiprocessing**: Implementing multiprocessing to achieve parallelism and speed up processing.
- **Access Control**: Extending the code to control which types of websites can be accessed.
- **Extended Requests**: Implementing additional request types like POST.

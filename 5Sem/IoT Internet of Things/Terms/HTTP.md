> [!FAIL] **PARADIGM:** [[Request-Reply]]

1. A client sends an HTTP request message to a server, which responds with an HTTP response message.
2. The client can send different types of requests such as below, and the server responds accordingly.
	**a. GET** to to retrieve information,
	**b. POST** to submit data,
	**c. PUT** to update or replace existing data,
	**d. DELETE** to remove data,
### IoT Use Case
In IoT, a sensor can send a request to a cloud server for processing and storing data. The server responds with a message confirming the successful processing and storage of the data.
#### Pros & Cons
##### Pros
- **Reliability:** The client is guaranteed to receive a response from the server, ensuring that the request is fulfilled.
- **flexibility:** The client can make different types of requests, and the server can respond with different types of responses.
- **Control:** The client has control over the request, and the server has control over the response.
##### Cons
- **Performance:** The client has to wait for the response from the server, which can affect performance, especially in a high-traffic environment.
- **Scalability:** The request-response pattern can become difficult to scale in a large distributed system with many clients and servers.
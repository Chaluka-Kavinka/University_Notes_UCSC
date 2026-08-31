> [!TIP] Overview
> Application Layer, is the top layer in both the OSI and TCP/IP models. It is the layer that provides services directly to the user and handles the high-level protocols used for network applications

---
# 1. The Client-Server Model

This is the primary architectural model for network applications.

- **The Client:** A process that initiates communication by sending a **Request** for data or services (e.g., a web browser).
- **The Server:** A process that is always on, listening for requests. It **Responds** to the client's request by providing the requested data or resource.
# 2. The World Wide Web (WWW)

The Web is an information system that allows documents and resources to be accessed over the internet.

- **URL (Uniform Resource Locator):** A unique address for identifying resources, such as `http://www.ucsc.cmb.ac.lk/img/logo.png`.
- **Web Browsers:** Software applications used to retrieve and display content from the web.

# 3. HTTP (Hypertext Transfer Protocol)

HTTP is the foundation of data communication for the web. The module covers several versions and characteristics:

- **Protocol Versions:**
    - **HTTP/1.0 (RFC 1945):** Uses **non-persistent connections**, meaning each request requires a new TCP connection.
    - **HTTP/1.1 (RFC 2616):** Uses **persistent connections**, allowing multiple requests and responses over a single TCP connection to reduce latency (RTT).
- **Stateless Protocol:** HTTP is stateless, meaning the server does not store information about previous requests from the same client.
- **HTTP Syntax:**
    - **Methods:** Core commands including **GET** (retrieve a document), **POST** (send data for processing), **HEAD** (get headers only), **PUT** (store body on server), and **DELETE** (remove document).
    - **Status Codes:** Ranges that indicate the result of a request: **200-299** (Successful), **400-499** (Client Error, e.g., 404 Not Found), and **500-599** (Server Error).
# 4. Web Servers

A web server can be either software (like Apache) or a dedicated hardware appliance. The sources describe the **seven steps** a web server takes to handle a request:

1. **Set up connection:** Identify the client host name and user.
2. **Receive request:** Parse the method, resource identifier, and version.
3. **Process request:** Analyze headers and body.
4. **Access resources:** Identify the resource via the "Docroot" or dynamic mapping.
5. **Construct response:** Determine status codes and headers like Content-Type (MIME).
6. **Send response:** Deliver the data to the client.
7. **Log transactions:** Record the activity for administrative purposes.

# 8. Supporting Application Services

- **DNS (Domain Name System):** A hierarchical database that translates human-readable domain names (like `www.google.com`) into IP addresses. It uses a tree structure starting from **Root servers** down to **Top-Level Domains** (.lk, .com) and specific **Authoritative servers**.
- **Other Services:** The module also introduces **Email**, **DHCP** (for dynamic IP assignment), and **FTP** (File Transfer Protocol).
## What is HTTP protocol?

- HTTP stands for Hypertext Transfer Protocol, which is a communication protocol used for transmitting data over the internet. It is the foundation of data communication for the World Wide Web.
- HTTP is a client-server protocol, which means that requests are sent by clients, such as web browsers, to servers, which then respond with the requested data. The data is typically in the form of HTML, CSS, JavaScript, images, and other types of files.
- HTTP uses a request-response model, where clients send requests to servers, and servers respond with the requested data. Each HTTP request and response consists of a set of headers, which contain information about the request or response, and a message body, which contains the data being transmitted.


## What is TCP Protocol?

- TCP (Transmission Control Protocol) is a transport layer protocol that is used to establish and maintain a reliable, end-to-end connection between applications running on different hosts over the internet. It provides a reliable, ordered, and error-checked delivery of data between applications.
- TCP is a connection-oriented protocol, which means that before data is sent, a connection is established between the sender and receiver. This connection is managed by a three-way handshake process, in which the client sends a SYN (synchronize) message to the server, the server responds with a SYN-ACK (synchronize-acknowledge) message, and the client sends an ACK (acknowledge) message to confirm the connection.
- Once the connection is established, TCP ensures that data is transmitted in the correct order, without errors, and without loss of data. It does this by dividing the data into segments, adding a sequence number to each segment, and retransmitting any segments that are lost or corrupted during transmission.
- TCP also includes flow control and congestion control mechanisms to ensure that data is transmitted at an appropriate rate and that the network is not overloaded with traffic.
- CP is used by many internet applications, including web browsing, email, file transfer, and remote login. It is one of the most widely used protocols in the Internet Protocol (IP) suite and forms the basis of many higher-level protocols such as HTTP, FTP, and SMTP.



## What are HTTP headers?

- HTTP headers are additional pieces of information that are sent along with an HTTP request or response between a client and a server. They provide metadata about the request or response, such as the content type, encoding, cache control, and more.
- HTTP headers are divided into two types: request headers and response headers.
    - Request headers: These headers are sent by the client to the server as part of an HTTP request. They provide additional information about the request being made, such as the user agent, the method being used (GET, POST, etc.), and the content type of the request body.
    - Response headers: These headers are sent by the server to the client as part of an HTTP response. They provide additional information about the response being returned, such as the content type, the cache control directives, and the server software being used.
- Some common HTTP headers include:
    - Content-Type: Indicates the MIME type of the response body
    - Content-Length: Indicates the length of the response body in bytes
    - Cache-Control: Specifies how the response should be cached by the client or intermediate proxies
    - User-Agent: Identifies the client software (such as a web browser) making the request
    - Set-Cookie: Sets a cookie in the client's browser



## What are some HTTP response codes? what does it mean? 2xx, 3xx, 4xx, 5xx

- 2xx (Successful): These codes indicate that the request was successful and the server was able to return the requested resource. Some examples include:
    - 200 OK: The request was successful and the server has returned the requested data
    - 201 Created: The request was successful and a new resource was created on the server
    - 204 No Content: The request was successful but there is no content to send back

- 3xx (Redirection): These codes indicate that the client must take additional action to complete the request. Some examples include:   
    - 301 Moved Permanently: The requested resource has been permanently moved to a new location
    - 302 Found: The requested resource has been temporarily moved to a new location
    - 304 Not Modified: The requested resource has not been modified since the last time it was accessed

- 4xx (Client Error): These codes indicate that the request was unsuccessful due to an error on the client side. Some examples include:
    - 400 Bad Request: The server could not understand the request due to invalid syntax
    - 403 Forbidden: The client does not have permission to access the requested resource
    - 404 Not Found: The requested resource could not be found on the server

- 5xx (Server Error): These codes indicate that the request was unsuccessful due to an error on the server side. Some examples include:
    - 500 Internal Server Error: The server encountered an unexpected condition that prevented it from fulfilling the request
    - 502 Bad Gateway: The server received an invalid response from an upstream server
    - 503 Service Unavailable: The server is currently unable to handle the request due to maintenance or overload




## What does cache control on http response mean?

- Cache-Control is an HTTP response header that specifies how the client, proxy, or browser should handle caching of the web content. It can be used by the server to control how long a particular resource should be cached and whether or not it should be cached at all.
- The Cache-Control header can contain several directives, which control the caching behavior of the client, proxy, or browser. Some of the most common directives are:

    - max-age: specifies the maximum amount of time in seconds that the resource can be cached before it is considered stale and must be revalidated with the server.
    - no-cache: specifies that the client, proxy, or browser must revalidate the resource with the server before using it, even if it is in the cache.
    - no-store: specifies that the client, proxy, or browser must not store the resource in the cache.
    - must-revalidate: specifies that the client, proxy, or browser must revalidate the resource with the server before using it, even if it is in the cache and has not expired.



## What is polling?

- Polling is a computer networking technique used to continuously check for the availability of new data or information from a remote server or device. In this technique, a client sends requests to the server at regular intervals to check for updates or changes in the data.
- The client repeatedly sends a request to the server and waits for a response, even if there is no new data available. This approach is often used in situations where the server does not have the ability to push new data to the client, such as in a client-server architecture.
- For example, polling is commonly used in web applications to check for updates to web pages or feeds. In this case, the client sends a request to the server at regular intervals to check for any changes in the content of the web page or feed.
- Polling can be resource-intensive and may lead to increased network traffic and slower response times. To address this, other techniques such as long polling and server-sent events (SSE) have been developed to improve efficiency and reduce resource consumption.




## What is long polling?

- In this approach, the client sends a request to the server, but the server does not immediately respond with the current state of the requested resource. Instead, the server waits until new data is available or a timeout occurs before sending a response to the client.
- This technique allows the server to push new data to the client as soon as it becomes available, reducing the amount of unnecessary network traffic and improving response times. Long polling is often used in situations where the data is not updated frequently, but the client needs to be notified immediately when new data becomes available.
- For example, long polling is commonly used in chat applications or online gaming, where real-time updates are required. The client sends a request to the server to check for new messages or game updates. If there is no new data, the server waits for a specified period of time before responding. If new data becomes available during this time, the server immediately sends a response with the new data to the client.
- Long polling can be more efficient than traditional polling because it reduces the number of requests sent to the server and allows for real-time updates without the need for constant client requests. However, it can also be more complex to implement and may require additional server-side infrastructure.




## Explain briefly what happens when you hit a url? explain DNS lookup

- When you hit a URL (Uniform Resource Locator), your web browser sends a request to the server that hosts the website. The server responds by sending back the HTML, CSS, and JavaScript files that make up the webpage, which are then rendered by the browser.
- The process of requesting a webpage involves several steps, including:
    - DNS lookup: The first step in loading a webpage is translating the URL into an IP address that the browser can use to locate the server hosting the website. This process is called DNS (Domain Name System) lookup, and it involves querying a DNS server to resolve the domain name in the URL to an IP address.

    - HTTP request: Once the browser has resolved the IP address, it sends an HTTP (Hypertext Transfer Protocol) request to the server. This request includes information such as the type of request (e.g. GET, POST), the URL of the requested resource, and any additional headers or data.

    - Server processing: The server receives the HTTP request and processes it, using server-side technologies such as PHP, Node.js, or Ruby on Rails to generate a response.

    - HTTP response: The server sends an HTTP response back to the browser, which includes the requested resource (e.g. HTML, CSS, JavaScript files), as well as any additional headers or data.

    - Rendering: The browser receives the HTTP response and begins rendering the webpage. This involves parsing the HTML, applying the CSS styles, and executing any JavaScript code.

    - Display: Once the webpage has been rendered, the browser displays it to the user.



## What is a URLs full form? Explain what a url is and the four parts it consists of The protocol in use The hostname of the server The location of the file The arguments to the file

- URL stands for Uniform Resource Locator. It is a string of characters that provides a way to locate a resource on the internet. A URL typically consists of four parts:

- The protocol in use: The protocol is the method used to retrieve the resource. Common protocols include HTTP (Hypertext Transfer Protocol) and HTTPS (HTTP Secure) for webpages, FTP (File Transfer Protocol) for file downloads, and SMTP (Simple Mail Transfer Protocol) for email.

- The hostname of the server: This is the domain name or IP address of the server that hosts the resource. For example, the hostname for the Google homepage is "www.google.com".

- The location of the file: This is the path to the specific file or resource on the server. For example, the path to the Google homepage is "/".

- The arguments to the file: These are optional parameters that are passed to the server along with the request. They are typically used to provide additional information or context to the resource being requested. For example, a search query might be passed as an argument in a URL.




## What is clickjacking? How do you fix it?

- Clickjacking is a type of web attack in which an attacker tricks a user into clicking on a hidden or disguised link or button on a web page, often by overlaying the page with a transparent layer or iframe. This allows the attacker to perform actions on behalf of the user, such as posting messages or stealing sensitive information.
- To fix clickjacking, there are several measures that can be taken:
    - Frame busting: One common technique is to use frame-busting code to prevent a page from being displayed within an iframe. This code detects if the page is being displayed within an iframe and if so, redirects the browser to the original page, breaking the attacker's overlay.

    - X-Frame-Options header: The X-Frame-Options header is another solution that can be used to prevent a page from being displayed within an iframe. This header is set by the server and specifies whether a page can be displayed within an iframe or not.

    - Content Security Policy (CSP): CSP is a security standard that can be used to prevent clickjacking attacks by allowing a web page to specify which domains are allowed to embed the page in an iframe. If an attacker tries to embed the page in an iframe from a domain that is not specified, the browser will block it.

    - User education: Another important measure is to educate users about the dangers of clicking on links or buttons on unfamiliar or suspicious web pages, especially if they are asked to provide sensitive information.




## What are some performance metrics for your website?

- Page load time: This is the time it takes for a web page to fully load in the user's browser. A slow page load time can result in a poor user experience and negatively impact search engine rankings.

- Time to first byte (TTFB): This is the time it takes for the server to start sending data back to the browser after a request is made. A high TTFB can indicate server performance issues.

- Render time: This is the time it takes for the browser to display the content on the screen after receiving the HTML, CSS, and JavaScript files. A slow render time can result in a poor user experience.

- Number of requests: This is the total number of requests made by the browser to load a web page. Reducing the number of requests can improve page load time and overall performance.

- Page size: This is the size of the web page in bytes. Large page sizes can result in longer load times and negatively impact user experience.

- Time to interactive (TTI): This is the time it takes for a web page to become fully interactive, meaning that all the necessary content has loaded and the user can interact with the page. A slow TTI can negatively impact user experience and increase bounce rates.

- Bounce rate: This is the percentage of users who leave the website after viewing only one page. A high bounce rate can indicate poor user experience, which may be due to slow page load times, poor content, or other issues.

In summary, there are several performance metrics that can be used to measure the speed and efficiency of a website, including page load time, time to first byte, render time, number of requests, page size, time to interactive, and bounce rate. Monitoring and optimizing these metrics can help improve the user experience and overall performance of a website.



## What do CDN or Content Delivery Networks do? When do you need a CDN?

- A CDN (Content Delivery Network) is a network of servers located around the world that are designed to deliver content, such as images, videos, and other static files, to users quickly and efficiently. When a user requests content from a website, the CDN will serve the content from the server that is closest to the user, reducing the distance the content has to travel and improving the website's performance and speed.
- Here are some situations where a CDN may be necessary:
    - High traffic websites
    - Global audience
    - Large file sizes
    - Security




## What is the difference between Client Side Renderring and Server Side Renderring?

- Client-side rendering involves sending a minimal HTML file to the client's web browser, which then loads the page and any required assets (such as JavaScript, CSS, and images) and renders the page on the client's device. This approach puts more of the burden of rendering on the client, which can result in faster page loads and a more responsive user interface. However, it can also be less SEO-friendly and may result in slower initial rendering of the page, particularly on slower devices or networks.
- Server-side rendering involves rendering the page on the server and then sending the fully rendered HTML file to the client's browser. This approach puts more of the burden on the server, which can result in slower page loads and a less responsive user interface. However, it can also be more SEO-friendly and can result in faster initial rendering of the page, particularly on slower devices or networks.



## What is Progressive Renderring

- Progressive rendering is a technique to show the most important parts of a web page to the user first, even before the entire page has loaded, in order to provide a faster and better user experience. This involves prioritizing the loading of critical content and deferring the loading of non-critical content until later, and can also include lazy loading and code splitting.



## What is the difference between Preloading and Prefetching resources? 

- Preloading refers to loading resources that will be used on the current page, such as images or scripts, before they are actually needed. This ensures that they are ready and available when they are needed, which can reduce page load times and improve the user experience.
- Prefetching, on the other hand, involves loading resources that will be needed on subsequent pages, such as links or images, in advance. This is done in the background while the user is still browsing the current page, so that the resources will be available and ready to be displayed quickly when the user navigates to the next page.



## What are service workers?

- Service workers are scripts that run in the background of a web application or website and are designed to improve the performance and offline functionality of the site. They can intercept network requests and cache resources such as images and JavaScript files, which can then be served quickly and efficiently from the cache instead of being downloaded over the network every time the site is accessed. This can lead to faster load times and a better user experience, especially on slower connections.
- Service workers can also provide offline functionality by allowing a website or application to work even when there is no network connection. When the user goes offline, the service worker can use the cached resources to continue serving the site or application, and then sync any changes with the server once the network connection is restored.
- Overall, service workers are a powerful tool for improving the performance and offline functionality of web applications and websites, and are an essential part of modern web development.
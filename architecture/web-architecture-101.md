# Web Architecture 101

---

![](/assets/1_K6M-x-6e39jMq_c-2xqZIQ.png)

### DNS

DNS stands for “Domain Name Server” at the most basic level DNS provides a key/value lookup from a domain name (e.g., google.com) to an IP address (e.g., 85.129.83.120), which is required in order for your computer to route a request to the appropriate server. Analogizing to phone numbers, the difference between a domain name and IP address is the difference between “call John Doe” and “call 201-867–5309.” Just like you needed a phone book to look up John’s number in the old days, you need DNS to look up the IP address for a domain. So you can think of DNS as the phone book for the internet.

### Load Balancer

Load Balancers make scaling horizontally possible. They route incoming requests to one of many application servers that are typically clones / mirror images of each other and send the response from the app server back to the client. Any one of them should process the request the same way so it’s just a matter of distributing the requests across the set of servers so none of them are overloaded.

### Web Application Servers

They execute the core business logic that handles a user’s request and sends back HTML to the user’s browser. To do their job, they typically communicate with a variety of backend infrastructure such as databases, caching layers, job queues, search services, other microservices, data/logging queues, and more. App server implementations require choosing a specific language (Node.js, Ruby, PHP, Scala, Java, C# .NET, etc.) and a web MVC framework for that language (Express for Node.js, Ruby on Rails, Play for Scala, Laravel for PHP, etc.).

### Database Servers

Databases provide ways of defining your data structures, inserting new data, finding existing data, updating or deleting existing data, performing computations across the data, and more. In most cases the web app servers talk directly to one, as will the job servers. Additionally, each backend service may have it’s own database that’s isolated from the rest of the application.

### Caching Service

A caching service provides a simple key/value data store that makes it possible to save and lookup information in close to O(1) time. Applications typically leverage caching services to save the results of expensive computations so that it’s possible to retrieve the results from the cache instead of recomputing them the next time they’re needed. An application might cache results from a database query, calls to external services, HTML for a given URL, and many more.

### Job Queue & Servers

Most web applications need to do some work asynchronously behind the scenes that’s not directly associated with responding to a user’s request. For instance, Google needs to crawl and index the entire internet in order to return search results. It does not do this every time you search. Instead, it crawls the web asynchronously, updating the search indexes along the way. Another example is to have priority queues to ensure that time-sensitive operations like sending password reset emails are completed ASAP.

### Full-text Search Service

Many if not most web apps support some sort of search feature where a user provides a text input (often called a “query”) and the app returns the most “relevant” results. The technology powering this functionality is typically referred to as “full-text search”, which leverages an inverted index to quickly look up documents that contain the query keywords. The most popular full-text search platform today is Elasticsearch.

### Services

Once an app reaches a certain scale, there will likely be certain “services” that are carved out to run as separate applications. They’re not exposed to the external world but the app and other services interact with them.

### Data (a, b, c)

Today, companies live and die based on how well they harness data. Almost every app these days, once it reaches a certain scale, leverages a data pipeline to ensure that data can be collected, stored, and analyzed.

The app sends data, typically events about user interactions, to the data “firehose” which provides a streaming interface to ingest and process the data.

The raw data as well as the final transformed/augmented data are saved to cloud storage.

The transformed/augmented data is often loaded into a data warehouse for analysis.

### Cloud Storage

Cloud storage is a simple and scalable way to store, access, and share data over the Internet. You can use it to store and access more or less anything you’d store on a local file system with the benefits of being able to interact with it via a RESTful API over HTTP.

### CDN

CDN stands for “Content Delivery Network” and the technology provides a way of serving assets such as static HTML, CSS, Javascript, and images over the web much faster than serving them from a single origin server. It works by distributing the content across many “edge” servers around the world so that users end up downloading assets from the “edge” servers instead of the origin server. This in turns means connection distances are shorter & speed of asset downloads is drastically improved.



https://engineering.videoblocks.com/web-architecture-101-a3224e126947



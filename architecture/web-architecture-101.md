# Web Architecture 101

---

![](/assets/1_K6M-x-6e39jMq_c-2xqZIQ.png)

### DNS

DNS stands for “Domain Name Server” at the most basic level DNS provides a key/value lookup from a domain name (e.g., google.com) to an IP address (e.g., 85.129.83.120), which is required in order for your computer to route a request to the appropriate server. Analogizing to phone numbers, the difference between a domain name and IP address is the difference between “call John Doe” and “call 201-867–5309.” Just like you needed a phone book to look up John’s number in the old days, you need DNS to look up the IP address for a domain. So you can think of DNS as the phone book for the internet.

### Load Balancer

Load Balancers make scaling horizontally possible. They route incoming requests to one of many application servers that are typically clones / mirror images of each other and send the response from the app server back to the client. Any one of them should process the request the same way so it’s just a matter of distributing the requests across the set of servers so none of them are overloaded.

### Web Application Servers

They execute the core business logic that handles a user’s request and sends back HTML to the user’s browser. To do their job, they typically communicate with a variety of backend infrastructure such as databases, caching layers, job queues, search services, other microservices, data/logging queues, and more. App server implementations require choosing a specific language (Node.js, Ruby, PHP, Scala, Java, C# .NET, etc.) and a web MVC framework for that language (Express for Node.js, Ruby on Rails, Play for Scala, Laravel for PHP, etc.).

### Caching Service

https://engineering.videoblocks.com/web-architecture-101-a3224e126947



Credit: https://dzone.com/articles/load-balancing-pattern


## What?
A load balancer is a traffic manager that distributes incoming client requests across all servers that can process them. The pattern helps us realize the full potential of cloud computing by minimizing the request processing time and maximizing capacity utilization. The traffic manager dispatches the request only to the available servers; hence, the pattern works well with scalable cloud systems. Whenever a new server is added to the group, the load balancer starts dispatching requests and scales up. On the contrary, if a server goes down, the dispatcher redirects requests to other available servers in the group and scales down, which helps us save money.

## Types
### Static Load Balancers
| Type                     | Desc                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| ------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Round Robin**          | is the most fundamental and default algorithm to perform load balancing. It distributes the traffic sequentially to a list of servers in a group. The algorithm assumes that the application is stateless and each request from the client can be handled in isolation. Whenever a new request comes in, it goes to the next available server in the sequence. As the algorithm is basic, it is not suited for most cases.                                                                                                                     |
| **Weighted Round Robin** | is a variant of round robin where administrators can assign weightage to servers. A server with a higher capacity will receive more traffic than others. The algorithm can address the scenario where a group has servers of varying capacities.                                                                                                                                                                                                                                                                                               |
| **Sticky Session**       | also known as the Session Affinity algorithm, is best suited when all the requests from a client need to be served by a specific server. The algorithm works by identifying the requests coming in from a particular client. The client can be identified either by using the cookies or by the IP address. The algorithm is more efficient in terms of data, memory, and using cache but can degrade heavily if a server starts getting stuck with excessively long sessions. Moreover, if a server goes down, the session data will be lost. |
| **IP Hash**                         |        is another way to route the requests to the same server. The algorithm uses the IP address of the client as a hashing key and dispatches the request based on the key. Another variant of this algorithm uses the request URL to determine the hash key.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |


### Dynamic Load Balancers
| Type                          | Desc                                                                                                                                                                                                                                  |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Least Connection**          | dispatches the traffic to the server with the fewest number of connections. The assumption is that all the servers are equal, and the server having a minimum number of connections would have the maximum resources available.       |
| **Weighted Least Connection** | is another variant of the least connection. It provides an ability for an administrator to assign weightage to servers with higher capacity so that requests can be distributed based on the capacity.                                |
| **Least Response Time**       | considers the response time along with the number of connections. The requests are dispatched to the server with the fewest connections and minimum average response time. The principle is to ensure the best service to the client. |
| **Adaptive or Resource-based**                              |    dispatches the load and makes decisions based on the resources, i.e., CPU and memory available on the server. A dedicated program or agent runs on each server that measures the available resources on a server. The load balancer queries the agent to decide and allocate the incoming request.                                                                                                                                                                                                                                   |

## Cloud
### AWS: Elastic Load Balancing (ELB)
[Amazon ELB](https://aws.amazon.com/elasticloadbalancing/) is a highly available and scalable load-balancing solution. It is ideal for applications running in AWS. Below are four different choices of Amazon ELB to pick from:

1.  Application Load Balancer is used for load balancing of HTTP and HTTPS traffic.
2.  Network Load Balancer is used for load balancing both TCP, UDP, and TLS traffic.
3.  Gateway Load Balancer is used to deploy, scale, and manage third-party virtual appliances.
4.  Classic Load Balancer is used for load balancing across multiple EC2 instances.

### GCP – Cloud Load Balancing
[Google Cloud Load Balancing](https://cloud.google.com/load-balancing) is a highly performant and scalable offering from Google. It can support up to 1 million+ query per second. It can be divided into two major categories, i.e., internal and external. Each major category is further classified based on the incoming traffic. Below are a few load balancer types.

-   Internal HTTP(S) Load Balancing
-   Internal TCP/UDP Load Balancing
-   External HTTP(S) Load Balancing
-   External TCP/UDP Network Load Balancing

### Microsoft Azure Load Balancer
[Microsoft Azure load balancing](https://azure.microsoft.com/en-us/services/load-balancer/) solution provides three different types of load balancers:

1.  Standard Load Balancer - Public and internal Layer four load balancer.
2.  Gateway Load Balancer - High performance and high availability load balancer for third-party Network Virtual Appliances.
3.  Basic Load Balancer - Ideal for small-scale applications.

## Open Source
### NGINX
NGINX provides [NGINX Plus](https://www.nginx.com/products/nginx/) and [NGINX](https://nginx.org/en/), modern load-balancing solutions. There are many popular websites, including Dropbox, Netflix, and Zynga, that use load balancers from NGINX. The NGINX load balancing solutions are high-performance and can help improve the efficiency and reliability of a high-traffic website.

### Cloudflare
[Cloudflare](https://www.cloudflare.com/load-balancing/) is another popular load-balancing solution. It offers different tiers of the load balancer to meet specific customer needs. Pricing plans are based on the services, health checks, and security provided.

-   Zero Trust platform plans
-   Websites and application services plans
-   Developer platform plans
-   Enterprise plan
-   Network services
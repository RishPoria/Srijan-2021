# Container and Container Orchestration

---

| Question   | Answer                                                            |
| ---------- | ----------------------------------------------------------------- |
| Writer     | Adarsh Yadav - Msc I year                                      |
| Editor     | Rishabh Poria                                                      |
| Status     | Edited |
| Plagiarism | 5%. [Report](https://github.com/RishPoria/Srijan-2021/blob/main/articles/plagReports/ContainerOrchestration.pdf)|

---
Consider working on a project and it works fine in one's machine, but when the same project is run on any other machine it doesn't work. This can be because of any dependency, or because of a different version of a library. Containers can prove to be helpful here. A container is a standalone package that encapsulates application code and all of its dependencies, so that the application can run in any environment. Containers give you portability, isolation, and packaging. Just wrap everything inside an image (containers are running instances of images), and other users can directly run this image. Containers can be thought of as lightweight, scalable, and isolated Virtual Machines (not an actual VM) in which one can run their applications. 

To illustrate the concept of containers further, suppose a developer is working on a web application that requires PHP 7.2. So, he installs PHP 7.2 on his local machine. Later, he updates the app to use PHP 7.2 to 8.0. As a result, all the developers working on the same web app will also need to update their versions of PHP. If some more such libraries or dependencies are updated,  all the developers will need to update everything again. But with containers, only one developer needs to update everything and create a new image; all the other developers can use that image, since it contains all the updated libraries and dependencies inside it.

![Containers vs. VMs](https://github.com/RishPoria/Srijan-2021/blob/main/imgs/ContainersVsVirtualMachines.png)

In the figure on the right, in the absence of containers, each application is running its copy of the OS (Guest OS). Whereas on the left, the containerized applications share the host OS and are hence, much more efficient and lightweight, and take less time to start. There are varieties of container runtimes available like Docker, Rocket etc. Docker is the most popular container runtimein use.

<!--
![VMs vs Dockers](https://github.com/RishPoria/Srijan-2021/blob/main/imgs/VMsvsDockers.jpg)
-->

## Container Orchestration

There are multiple container orchestrations available, like Kubernetes and Docker Swarm, which automate container operations. Kubernetes is the most popular container orchestrator. Developed by a team at Google, it was later donated to the Cloud Native Computing Foundation (CNCF) and became open source. It eliminates many of the manual processes involved in deploying and scaling containerized applications. One can cluster together groups of hosts running containers, and Kubernetes helps one manage those clusters efficiently.

To understand the concept of Kubernetes and what can be done with Kubernetes, consider the case of a shopping website.

**Case 1:** Suppose a server is hosted only in the Delhi region, to handle all requests from India. But due to some reason (like hardware failure), the server goes down, implying that the site goes down as well. Therefore the website should be hosted in multiple regions in India like Delhi, Mumbai, and Kolkata. This is called **high availability**. Problems like hardware failures do not bring the application down, because there are multiple instances of the application.

**Case 2:** Suppose there is very high load on the Delhi server. This can be handled by sending traffic to other servers. So **load balancing** is needed to balance the traffic in all the regions.

**Case 3:** Suppose there is a sale and server traffic increases in all the regions. So the server need to be scaled to handle all the traffic. Once the sale is over, they need to be scaled down again to prevent wastage of resources. Therefore, a method to easily **scale up and down** according to requirements is required.

**Case 4:** Suppose the website has to be updated during the sale, and that needs to be done without any downtime. Here, **zero downtime deployment** is needed.  

**Case 5:** As the payment service goes down, none of the other services in a microservice architecture (see image) should suffer. A **Health check and Self-healing** for all services can achieve this. If anything goes down, it automatically heals, which means automatic restart of the service.

![Monolithic Application](https://github.com/RishPoria/Srijan-2021/blob/main/imgs/MonolithicApplication.png)

Using Kubernetes, one can solve all the above problems. There are lots of other features available for exploration as well. It is open-source, used by different organizations, and lots of new features are added in every version. Many companies are getting a head start on Kubernetes and joining the revolution. By using containers and container orchestration, organizations can build and deploy horizontally scalable lightweight applications across multiple types of server hosts, cloud environments, and other infrastructures more effectively and efficiently.

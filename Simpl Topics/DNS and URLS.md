## What happens when we type a URL (www.google.com)

### URL stands for Uniform Resource Locator. 

URL is the address of the website. It is a **reference** to a **resource** on the internet, be it images, hypertext pages, audio/video files, etc. 

![dns1](./dns_url.png)

1. **The protocol**, also known as the scheme, is the first part of a URL. 
    - It represents the **sets of rules that decide how files are displayed, formatted, or transferred across the web**. For example, when an address is entered in the browser, the **http** part , which stands for **hypertext transfer protocol**, tells it that the page is to be displayed in **hypertext format (HTML)**. 

    - Other protocols include the **file transfer protocol (ftp)** for transferring files and **single mail transfer protocol (SMTP)** for used by mail servers to send emails. 

2. **The subdomain**, The most common subdomain is **‘www’** which a general symbol for any resource on the web. However, it is common to specify the type of resource that the browser should deliver. 

3. **The top level domain (TLD)** is also known as the **domain extension**. It is the **‘com’** that appears at the end of simple websites addresses like bing.com. This part specifies what kind of content will be on the website. **‘.com’ was primarily used for commercial sites** (although today it’s used to indicate any website), whereas **‘.org’** is usually used to indicate that the website is that of an organization. 

4. **The port** is a **reserved channel** used for specific purposes. Different types of servers will use different ports. Web server ports differ from file server ports, for instance. The default port for standard **HTTP servers is 80**, whereas secure websites use **HTTPS which requires port number 443**. (**SSH defaults to Port 22**)

5. **The path** used to show which **directory** on server stores the resources (files, videos, audio, etc.) that are being requested. Nowadays, the path that appears in most URLs these days don’t forcibly reflect the directory structure on the server. Instead, **paths are used to identify a route in the navigational structure of the website**.

### IP Addresses 

An **IP address** is a unique address that **identifies a device on the internet or a local network**. IP stands for **"Internet Protocol"**, which is the set of rules governing the format of data sent via the internet or local network.

An IP address is a **string of numbers separated by periods**. IP addresses are expressed as a **set of four numbers** — an example address might be **192.158.1.38**. Each **number in the set can range from 0 to 255**. So, the full IP addressing range goes from 0.0.0.0 to 255.255.255.255.

### DNS

**DNS** (**Domain Name System**) **maintains and maps** the name of the website, ie: **URL**, and particule **IP** (**Internet Protocol**) address it links to. 

Every **URL** on the internet has a unique **IP** address which is **of the computer which hosts the server of the website requested**.


### What happens whe we enter a URL: 

1. Browser checks (its own) **cache** for **DNS** entry to find the corresponding **IP address** of website. 

    It looks for the following cache. If not found in one, then continues checking to the next until found. 
        - Browser Cache 
        - Operating Systems Cache 
        - Router Cache 
        - **ISP** Cache

2. If not found in cacne, **ISP's (Internet Service Provider) DNS server** initiates a **DNS query** to find **IP address** of server that hosts the domain name.
    
    **The requests are sent using small data packets** that contain information content of request and **IP address** it is destined for. 

3. Browser initiates a **TCP (Transfer Control Protocol)** connection with the server using synchronize(**SYN**) and acknowledge(**ACK**) messages. 

4. Browser sends an **HTTP** request to the web server. **GET** or **POST** request. 

5. Server on the host computer **handles that request and sends back a response**. It assembles a response in some format like **JSON, XML and HTML**.

6. Server sends out an **HTTP response** along with the **status of response**. 

7. Browser displays **HTML** content. 

8. Browser may send more requests for additional objects embedded in the **HTML** like images, css, javascript. 

8. Finally Done....


### Note: A group of DNS Records are stored as a Routing Table (Even our Router Caches a Routing Table)

### HTTP Verbs: 

- **GET** - Read / Get
- **POST** - Create New / Add
- **PUT** - Update / Replace 
- **PATCH** - Update / Modify 
- **Delete** - Delete 


## What is REST ?

**REST** is an acronym for **REpresentational State Transfer**.

**REST** is an **architectural style for sending requests**. 

It has a **set of guiding priciples and constraints** that must be satisfied if a service interface needs to be referred to as **RESTful**

A **Web API (or Web Service)** **conforming to the REST architectural style** is a **REST API**.

There are six guiding priciples for REST: 

1. **Uniform Interface**

2. **Client-Server** (Seperation of concerns ie. **separating the user interface concerns (client) from the data storage concerns (server)**)

3. **Stateless** mandates that **each request from the client to the server must contain all of the information necessary to understand and complete the request**.

    **The server cannot take advantage of any previously stored context information on the server.**

    **The client application must entirely keep the session state.**

4. **Cacheable** 

5. **Layered System**

6. **Code on Demand** (optional)

## Idempotent in REST 

One of the important aspects of REST (or at least HTTP) is the concept that some operations (verbs) are **idempotent**.

The **PUT** method is **idempotent**. 

An **idempotent** method means that the **result of a successful performed request is independent of the number of times it is executed**.

From a **RESTful** service standpoint, for an operation (or service call) to be **idempotent**, clients can make that **same call repeatedly while producing the same result**.

**Note** that while idempotent operations produce the same result on the server (no side effects), **the response itself may not be the same** (e.g. **a resource's state may change between requests**).

The **PUT** and **DELETE** methods are defined to be **idempotent**. 

However, there is a caveat on DELETE. The problem with DELETE, which if **successful would normally return a 200 (OK) or 204 (No Content)**, will **often return a 404 (Not Found)** on **subsequent calls**, unless the service is configured to **"mark" resources for deletion without actually deleting them**.

## DHCP Server (How My Machine Go IP?)

A **DHCP Server** is a **network server that automatically provides and assigns IP addresses**, **default gateways and other network parameters to client devices**. 

It **relies** on the **standard protocol** known as **Dynamic Host Configuration Protocol or DHCP** **to respond to broadcast queries by clients**.

A **DHCP** server **automatically sends the required network parameters** for **clients to properly communicate on the network**. 

**Without** it, the **network administrator has to manually set up every client that joins the network**, which can be cumbersome, especially in large networks.

**DHCP** servers usually **assign each client with a unique dynamic IP address**, which **changes when the client’s lease for that IP address has expired**.

![dns2](./dns_dhcp.png)


_This should be enough_
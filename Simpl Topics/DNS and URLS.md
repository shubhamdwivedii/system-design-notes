## What happens when we type a URL (www.google.com)

### URL stands for Uniform Resource Locator. 

URL is the address of the website. It is a **reference** to a **resource** on the internet, be it images, hypertext pages, audio/video files, etc. 

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
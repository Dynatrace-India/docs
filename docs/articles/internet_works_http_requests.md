---
layout: default
title: How Browsers Sends HTTP Requests?
nav_order: 2
parent: Blog
permalink: /blog/internet_communication/http_requests
---
<button class="btn js-toggle-dark-mode">Switch to dark mode</button>

<script>
const toggleDarkMode = document.querySelector('.js-toggle-dark-mode');

jtd.addEvent(toggleDarkMode, 'click', function(){
  if (jtd.getTheme() === 'dark') {
    jtd.setTheme('light');
    toggleDarkMode.textContent = 'Switch to dark mode';
  } else {
    jtd.setTheme('dark');
    toggleDarkMode.textContent = 'Return to the light side';
  }
});
</script>

# Internet Communication - How Browsers Sends HTTP Requests?
## It’s time to see how the browser communicates with the webserver

In my previous article on how technology works, I covered how browsers render webpages on the screen after receiving a response from the server. As a quick recap, you can visit my article at this link to understand how technology works.

![Technology](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/k82i2kwh16zb8pcx4pfb.png)
This week we will be studying how the browser initiates an HTTP request to get the response from the server. We will go through each step that is shown in this flow.

---
## How browser sends HTTP requests?

![How browser sends HTTP requests?](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/rv6iqwhcqdw9349bq0hs.png)
High-level communication flow from the browser to the server which goes through certain steps before sending/receiving the data. This is not one-way communication. It is the 2-way street where before reaching the server, the browser tries to connect to the server and vice-versa. If anyone step fails to complete, the browser will not successfully reach the destination server with the IP.

### #1 Looking for DNS

![Looking for DNS](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/y5scw1hr6i3uig4nm13u.png)
Finding DNS is like searching for the love of the HTTP request’s life. It keeps searching all the available cache servers before searching in global DNS servers (Like Matrimony sites). 4 types of cache are available by default, Browser, OS, Router, and ISP. There are other types as well where we can use our own caching servers. Those advanced topics we will see in the future. For now, knowing the type of available caches is important.

### #2 DNS Server — How it works?

![DNS Server — How it works?](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/f67swnniaspamspb1f0z.png)
Once the request goes out of the browser after checking the ISP cache for the IP address for the DNS, it hits multiple DNS servers across the internet to find the right IP address for you (If you can’t find a girl in this country you can always try in others). This uses a recursive method to find the different name servers (NS) associated with the domain name. So the search keeps happening until it finds the right NS. This request nature is small packets that contain details of the source and destination IPs. When it hits the right name server, it gets the DNS address of the DNS and is sent back to the browser.

### #3 TCP/IP Connection
![TCP/IP Connection](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/e8l8oukon9drwc7gr4gn.png)
It follows a 3-way handshake to get this done, like asking if it is available to take a new connection from the server. If the server responds with yes, then the browser will send the acknowledgment to the server.

### #4 Sending HTTP requests
![Sending HTTP requests](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/frt5xjwstbo5eia2wj42.png)
With the type of request specified, the browser will send the information to fetch the required web pages from the server. It uses different headers to send the request. Based on this header authentication, the server will respond to the request and send the HTML formatted web page to the browser.

---
## Summary:
In summary, if we see step by step sending a request to the server/datacenter, it all starts with the user who enters the web address or interacts with the application they are using. Before sending requests to the internet, the browser checks for its internal cache and then checks the OS cache then it checks for router cache. If it fails to find the right IP, it goes on and checks with Internet service providers. Even now if it fails to get the right IP for the mentioned DNS, it starts to check in internet DNS servers that are globally available. 

In DNS, each domain has different nameservers where it connects to respective servers that hold these domain names. For example, .com (root level & top-level domain) will go to a different nameserver, and google (2nd level domain) will go to another nameserver. Then now this google.com will go and check for the third-level domain name server in the Google data center. This process is called DNS lookup. Here browser will get the complete IP address of the server where it should communicate or send requests to. 

Before sending an HTTP request, the browser does a 3 level handshake with the server which includes, SYN (synchronize) and ACK (acknowledge) requests. This uses TCP/IP protocol. 

Once the server sends the response as it is ready to accept new requests, the browser acknowledges it and starts to send HTTP requests (GET/POST) with headers. 

---

**_Happy reading. I hope you all had a great week. Keep learning and never give up on your dreams._**

This article is also published in [LinkedIn](https://medium.com/r/?url=https%3A%2F%2Fwww.linkedin.com%2Fpulse%2Finternet-communication-how-browsers-sends-http-vishruth-harithsa), [Medium](https://medium.com/r/?url=https%3A%2F%2Fmedium.thetechnologist.in%2Finternet-communication-how-browsers-sends-http-requests-27f56c6bf9e5), [Dev Community](https://dev.to/theharithsa/internet-communication-how-browsers-sends-http-requests-133b), [Transform Docs](https://dt-transform.com/docs/blog/internet_communication/http_requests)

## Author Information
This article is written by [Vishruth Harithsa](https://dt-transform.com/docs/authors/vishruth_harithsa).
---
layout: default
title: How Browsers Render Webpages?
nav_order: 1
parent: Blog
permalink: /blog/internet_communication/rendering_webpages
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

# Internet Communication - How Browsers Render Webpages?
In this article, we will spend more time looking at the diagrams than reading text so 6 diagrams explain how internet communication works. In this article mainly we focus on browser rendering HTML pages. Let's start with the overall flow diagram of how communication happens between the client (Web browser) and the server (Backend). 

![How Tech Works?](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/bot6krwkd555ob2du8x9.png)

Once the browser receives the response from the server as shown in the above diagram (10), the browser starts its work in displaying the received HTML code onto its canvas (window). 

---

## Rendering Webpages
Rendering and painting webpages on the screen are divided into 4 steps to make your understanding better about the process. There are in-depth steps that are involved to render webpages as it is the topic of some other season.

![Rendering Webpages](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/yriotwlj0gy89j1rdse0.png)

It all starts with the user who enters the URL in the address bar of the browser. You can see the detailed article that talks about the communication flow and it comes under the primary skillset of a performance engineer. There are around 105 steps that take place before the browser displays a webpage to you. 

### #1 Content-Type

![Content-Type](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/zdv4sn9pie7xr0sgz99i.png)

In this step, the browser will mostly understand the content it is getting to render by the type it is sent by the request header. Once it detects the type, the browser engine will start taking control in the next step. 

### #2 Render Tree Construction

![Render Tree COnstruction](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/7fe7tnenomp0ggf8j8rg.png)

In render tree construction, there are two trees where it constructs the DOM tree and CSSOM. By combining those 2 trees, the final output will create and this is the render tree.

### #3 Layout Operation

![Layout Operation](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/lf7znkji14umhmgus7ly.png)

This happens as soon as the render tree is constructed. In this stage, a box model is created based on the screen size and device data it captures from inbuilt device APIs. Upon the creation of the box model, it starts painting the contents on the screen. Will see the flow of it tomorrow. 

### #4 Rasterizing/Painting & Composition Operation

![Rasterizing](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/b0q7h3g6ycciy5dr0xk6.png)

In this, we discuss how the browser paints all the contents that are collected and rendered in the previous layout operations. It collects the data and creates layers using GPU (Modern Browsers). Once Layers are created, it will start painting on the screen and this happens by splitting each layer into each type of content like text, images, or rich media. This will happen for each layer that is painted on the browser window. Finally, we see a clean and smooth-looking web page (If it is designed well). 

---

## References
- [How Browsers Work: Behind the scenes of modern web browsers](https://www.html5rocks.com/en/tutorials/internals/howbrowserswork/)
- [Render-tree Construction, Layout, and Paint](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/render-tree-construction)
- [How the browser renders a web page? — DOM, CSSOM, and Rendering](https://medium.com/jspoint/how-the-browser-renders-a-web-page-dom-cssom-and-rendering-df10531c9969)

---

Happy learning and feel free to ping me if you have any doubts in here or even on LinkedIn. 

This is published in [LinkedIn](https://www.linkedin.com/pulse/internet-communication-how-browsers-render-webpages-vishruth-harithsa), [Dev Community](https://dev.to/theharithsa/internet-communication-how-browsers-render-webpages-5go1), [Medium](https://medium.thetechnologist.in/4563786653e4), [Transform Docs](https://dt-transform.com/docs//blog/internet_communication/rendering_webpages)

---

## Author Information
This article is written by [Vishruth Harithsa](https://dt-transform.com/docs/authors/vishruth_harithsa).
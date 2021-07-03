---
layout: default
title: Vishruth Harithsa
nav_order: 1
parent: Authors
permalink: /authors/vishruth_harithsa
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

# Vishruth Harithsa
## Articles Contributed
1. [How Browsers Render Webpages?](https://dt-transform.com/docs/blog/internet_communication/rendering_webpages)
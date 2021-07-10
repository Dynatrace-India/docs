---
layout: default
title: Blog
nav_order: 2
has_children: true
permalink: /blog
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

# Blogs
In here you can find some of the articles that are written by our team members which are also published in other sites as well. 

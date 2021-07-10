---
layout: default
title: Authors
nav_order: 5
has_children: true
permalink: /authors
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

# Authors
{: .no_toc }
Here you will find the information about the authors of the site who contributed to pubish articles and wrote the documentations to help the site grow. 
This is under improvement all the time and in this page you can find the list of authors and little bit of inofrmation about them.

## Contributors
1. [Vishruth Harithsa](https://dt-transform.com/docs/authors/vishruth_harithsa)
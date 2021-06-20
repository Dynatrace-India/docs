---
layout: default
title: Applications
nav_order: 3
permalink: /apps
has_children: true
---
<button class="btn js-toggle-dark-mode">Switch display mode</button>

<script>
jtd.setTheme('dark');
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
# List of Applications
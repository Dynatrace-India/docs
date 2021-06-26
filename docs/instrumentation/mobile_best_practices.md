---
layout: default
title: Best Practices
nav_order: 1
parent: Mobile Instrumentation
grand_parent: Instrumentation
permalink: /instrumentation/mobile/best_practices
---
<button class="btn js-toggle-dark-mode">Switch to dark mode</button>

<script>
const theme = localStorage.getItem('theme');
	if (theme === "dark") {
		document.documentElement.setAttribute('data-theme', 'dark');
	}

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

# Best Practices To Apply While Doing Mobile Instrumentation With Dynatrace
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## User Tagging:
- Tagging a user in mobile instrumentation needs to be done correctly to capture each session so, the best way to do it is adding the tag in 3 places.
- One, at the start of the application (Splash Screen) with the device ID. This will capture and name the session with device ID. 
- Two, once user is logged in and homepage comes, tag a user at that part, and send it to Dynatrace. This time user tag would be username, email, or a unique ID which you want to pass. 
- Third, make sure you are not passing any user tag from anywhere even after logging out from the application because, Dynatrace tags the session with the tag that is passed at last. 
- These steps can be applied for both iOS and Android. 

---

## Auto/Manual Instrumentation:
- Auto Instrumentation is an easy way to capture every touch that user performs with the application. Dynatrace auto-instruments every touch by default. 
- Network requests are also captured automatically, and the user action naming of each user action is done like this,
    - If it is a button, this will take the text that is there in the view and name the user action as “Touch on Button Name”
    - If there is no text is specified in the view/button, Dynatrace auto-instrumentor takes the name of the parent layout like Relative, Linear or Constraint Layout as “Touch on Relative Layout:”
    - In iOS it takes the name of respective view layouts.
- To overcome this, we need to manually instrument the user action and give names that are easy for us to Identify. 
    - We could try adding user action naming rule in Dynatrace if the action detected is unique but if it is not unique and is naming different actions with the same name, we should go for manually adding user actions.
- Synchronous Calls: Dynatrace Auto-Instrumentor captures network requests automatically and map it under current user action. If there are multiple synchronous calls are involved, it will not be able to capture if the call is closed and another call is made. This is true in some cases and in some cases Dynatrace auto-instrumentor will capture. If calls are async, Dynatrace will capture complete network requests.

---

## Crash Analytics:
- Dynatrace auto-instrumentation detects the crashes automatically. For iOS and Android, it captures the crashes and report it to Dynatrace portal. 
- This can be enhanced more and get the code level data by uploading symbolic files for both iOS and in Android.

---

## Alerts:
- When it comes to alerting, Dynatrace automatically uses its AI capabilities to notify problems or the crashes that occurs in the mobile application
- Anyhow, you can integrate those alerts so that it will notify you via Emails, Slack, Trello, OpsGenie, SNOW and many other Incident Management Systems. 

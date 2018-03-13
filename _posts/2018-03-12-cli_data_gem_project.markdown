---
layout: post
title:      "CLI Data Gem Project"
date:       2018-03-13 01:17:42 +0000
permalink:  cli_data_gem_project
---


This project proved highly valuable to me as it both reinforced the course's OO Ruby curriculum and introduced  me to more nuance in web scraping. I chose to pull the official team page for the Notre Dame men's basketball team. Though I had a clear idea of how I wanted to organize the project from the beginning, there were several road bumps along the way which were valuable learning experiences.

1. Dynamic HTML creation - After breezing through the initial stages of my project, I hit an impasse when attempting to scrape each individual player's statistics. Despite being clearly visible on the webpage, the stats were nowhere to be found in the HTML document. Eventually, I learned that the HTML file made use of a Javascript function to pull the information from an XML file elsewhere on the website. After that, it was relatively simple to use Nokogiri to parse that XML page.

2. Testing - Towards the end of the project, my workflow became frequently interrupted each time I wanted to test my application. After tweaking a line of code, I would have to wait for all of my target website's data to load and be parsed before inspecting the results in pry. I realized that for larger projects I'll have to implement a faster method for testing. This would likely include creating dummy hashes in a spec file and more tightly compartmentalizing my project. 

3. Navigation Menu Class - As my project grew more complicated, I had to create several methods corresponding to navigation menus in the CLI. These methods all share basic features which makes them ripe for codification viz a new class. In my case, it probably would have been more work to separately define this new class. On a larger project, however, it would be a necessity.

4. Adding new categories - Partly to test this project's scalability, I went back and added another statistical category to my app. This required manual creation of several new variables and one new function. Obviously there are limits to automation in web scraping, but there was definite room for improvement in this area. 


These challenges helped me to understand the importance of time management when developing a project. At any given time, one can either be organizing or building. Organizing involves things like abstracting methods into classes, or finding a better way to test your program. Building involves writing the lines of code which actually make your program work. Obviously the larger and more complex the project, the greater amount of time spent organizing versus building. My goal is to learn how to better plan allocation between the two.



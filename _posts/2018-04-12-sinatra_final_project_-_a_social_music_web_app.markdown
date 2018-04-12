---
layout: post
title:      "Sinatra Final Project - A Social Music Web App"
date:       2018-04-12 17:24:50 +0000
permalink:  sinatra_final_project_-_a_social_music_web_app
---


The most important lesson I learned from my last project was the need to balance organization/code abstraction with building the application's functions. In this regard, I view this project as a major step forward. Before I wrote a single line of code, I mapped out all my user classes and their relations. I also created my entire file structure in advance. Better preparation allowed me to create a more complex application which mirrored the initial concept I had for this project. Still, there was room for improvement on the style and formatting end - more on that later. 

I built an site to connect people interested in live music. There are four models in the application - Show, Venue, Artist, and Fan. Shows belong to each of the other three user classes, but they can only be created by a Venue. It follows that the three user classes can relate to one another by the shows they participate in - hence the social element of this project. It's beyond the scope of what we've covered in the course so far, but I'd like to extend this project so that user classes could relate to one another in multiple ways. For example, fans could 'like' a particular artist, and then receive a feed of that artist's upcoming shows or announcements on their home page. Even better, fans could connect with each other directly to discuss artists and shows that they're excited about. I personally am excited to begin the Rails section of the course, as I expect it will allow me to better handle these permutations. 


Of course, there was still much to learn from this project itself. At the onset, I underestimated the difficulty of styling and formatting my webpages after the content and functionality was complete. While the underlying Ruby code is well organized and abstracted, my HTML layouts and CSS selectors are very much ad-hoc and inefficient. If I'd planned ahead, I would have had more time to style my site the way I envisioned it. This is important for at least two reasons:

1. In a professional environment, it may not directly fall upon me to implement a site's design, but I'll need to keep in mind the designer's needs. I won't be the only one whose time is wasted if my code is difficult to render on the page.
2. Building on a lesson from my previous job, people simply won't use your application if it doesn't look good and/or isn't easy to use. When I worked on a trading desk, I built a couple applications in VBA which I thought would be very useful to my colleauges. At first I was disappointed when they didn't seem interested. Then I cleaned up the design, and added a few simple navigation tools. My new version was a much greater success, despite its functionality being basically the same. 

The upshot of all this is - don't just throw around <h1> tags as placeholders and forget about them until the end.

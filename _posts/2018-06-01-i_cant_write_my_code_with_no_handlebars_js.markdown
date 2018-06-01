---
layout: post
title:      "I (can't) write my code with no Handlebars(.js)"
date:       2018-06-01 04:57:15 +0000
permalink:  i_cant_write_my_code_with_no_handlebars_js
---

For this portfolio component, I added features to an existing project as opposed to starting a new application from scratch.  Using the jQuery and AJAX I studied in the past month, I sought to make my [Bond Desk](http://odeabren.com/starting_to_bring_it_all_back_home) application more user friendly. As I wrote in the last post, efficient information retrieval is key for Bond Desk users. This portfolio component's requirements involved rendering content to the DOM without a redirect, which dovetailed with my overall priorities for the project. With growing complexity came several important lessons:

* Refactoring: I'd benefitted to this point from Rails' clear conventions on file and class structure, but managing Javascript scope proved to be a more challenging. Initially, I placed all my JS code in <script> tags and didn't concern myself with structuring the asset pipeline or scoping my variables. I was eager to make my site look more professional with JS, but should have stopped after completing each function and refactoring the code. I'm trying to create a habit of: (build single purpose function) => test => refactor => test => commit.
* Finer points of jQuery: It seems that a developer working in this language has a lot of latitude in solving the myriad issues that crop up when manipulating the DOM. I really enjoyed having to think creatively about these issues. An example: my code fires off an AJAX get request when a user hovers over a list item, then formats and renders the response on the page. But what if by the time a response is received, the user has moved her cursor over a different item in the list? In my case, responses from both the original list item and the new item could be displayed simultaneously. I prevent this by scoping a requestCounter variable outside the .mouseenter() function, and then setting a local counter variable = requestCounter. I also increment requestCounter upon .mouseexit(). Finally, I test whether the local counter is still == to requestCounter after the AJAX response is received. If the cursor has moved to a different element, the test will fail and the response will not be displayed.
* ActiveModel::Serializer: An extremely powerful tool which saved me a lot of time and made my code more efficient. JS can be a little cumbersome when handling API responses, so ::Serializer's custom class methods do well to render pre-formatted JSON objects. Also, explicit serializers are vital for avoiding wasteful API calls. 

There's still much more work to be done in terms of applying jQuery more broadly in my application. Also, in my last post, I mentioned the goal of adding a dynamic search bar - it turns out that will likely require PHP. We haven't covered that in the course yet, so it will have to wait for now. 



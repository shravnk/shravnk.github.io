---
layout: post
title:      "(Starting to) Bring it All Back Home"
date:       2018-05-11 23:00:15 +0000
permalink:  starting_to_bring_it_all_back_home
---


In anticipation of the Rails Portfolio Project, I began thinking about how I could improve upon the applications I used at my previous job on a sell-side bond trading desk. The first thing that came to mind was our infamously cumbersome system for recording trades and view trade history (Bloomberg TOMS). It's a really good example of software inertia within an organization or industry: this system had persisted at least a decade past its shelf life despite its universally acknowledged inefficiency. That's partly due to the complex entanglement of financial and regulatory infrastructure which could be costly to disrupt. But TOMS also persisted in part simply because people in the industry had spent a long time mastering it, and would be resistant to starting all over again. So when I set out to build a trading system prototype, I knew two things would be absolutely imperative:

1. The process for recording a trade should be as simple as possible. When you're submitting a form dozens of times per day, the cost of any inefficiency is quickly compounded.
2. The most pertinent information for each element* of the trading ecosytem should be readily accessible. An example to illustrate: a client expresses interest in a particular bond. You quickly need to know which other counterparties have been most active in that bond or view the bond's most recent trades. Given the often frenetic pace of these inquiries, the results should be 2 clicks or a simple search away.

On these terms, I think that my project was successful. The new trade form is straightforward, and depending on the user's route to the page, much of the trade's information is pre-filled. Per industry convention, only traders are able to directly submit trades. Salespeople can book trades with a 'pending' attribute - at any time a trader can confirm the trade with no more than two clicks.

In keeping with my theme of click minimization, I designed the site so that a summary of any bond, client, trader, or salesperson's activity was no more than two clicks away. This could become unwieldy as the project scaled to thousands of clients and bonds, and the project would likely require a search function. I would like to implement a single search bar in the overhead nav bar which instantly sorted results by category. Again, after learning more about Javascript in the next unit, I expect to be able to build this feature.

I'm also eager to add data visualization and outside financial data (e.g. on the U.S. Treasury market). Both will require independent learning after I'm finished the course. With these portfolio projects, it's been both humbling and exciting to see how expansive a developer's breadth of knowledge can grow.


*Trader, Salesperson, Client, Bond, Transaction

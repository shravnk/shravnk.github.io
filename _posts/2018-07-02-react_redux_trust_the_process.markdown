---
layout: post
title:      "React/Redux: Trust the Process"
date:       2018-07-02 14:31:50 +0000
permalink:  react_redux_trust_the_process
---


My final Flatiron project promised to be both challenging and exciting because of the more advanced material covered in the final two modules of the curriculum. Prior to this section, my previous amateur interest in programming served me well: the Ruby I learned mirrored some of the characteristics of Python I had encountered before. React and Redux, however, involved foreign concepts which were not intuitive to me at first. JSX, stateless components, and the action/reducer file structure seemed to introduce unneccessary complications, especially after I felt I had just begun to master front-end Rails applications. This was of course to change as I advanced through my final project. 

The goal of this project was to create a single HTML page application with a React front end and a Rails back end. React (and Redux) handle external API calls and data presentation. Rails handles user authentication and settings. In keeping with my pursuit of a position in the FinTech industry, I wanted to familiarize myself with a financial data provider's API. Bloomberg would have been the obvious choice here. But without a data license, I was forced to look elsewhere.

Fortunately I discovered IEX's API, which was well-documented and allowed access to a wealth of information. I was familiar with IEX's egalitarian ethos after reading the popular book *Flash Boys*. As a developer, was cool to see that the company's public and user-friendly API reflected those values.

In my previous jQuery project, I described difficulties making an internal API call and displaying data based on a user's hover state. My solution worked, but it was rather inelegant and suffered from performance issues. This time around, I had a similar but more ambitious goal. When a user hovers over a security, I wanted to display its price history in a chart. My solution involved isomorphic-fetch, react-bootstrap-table, and react-chartjs. These packages allowed me build a nimble and visually appealing feature without writing a ton of code. 

What those packages all benefit from is React's asynchronous rendering and Redux's memory efficiency. In this application, I no longer had to worry about setting timeouts for my API requests. React simply renders a component when the state changes, and Redux ensures that only relevant state changes trigger the component render. It took time to understand how to structure an application along those guidelines, but it made this and future projects much simpler.

Being a developer is a project of lifelong learning, which not coincidentally is something I aspire to. It's a great ideal, but you have to allow room for frustration. Learning React or any unfamiliar concept is simply not going to be immediately rewarding. You just have to trust the process. 


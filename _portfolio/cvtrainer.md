---
layout: post
title: Computer Vision Trainer
thumbnail-path: "img/cvtrainer-main.png"
short-description: Interface design to help computers learn. Bootstrap and Angular

---

{:.center}
![]({{ site.baseurl }}/img/cvtrainer.png)

{:.center}
[See code on Github](http://saraguittarclark.github.io/cvtrainer/){:target="_blank"}

## Explanation

My task was to create an interface where "human operators ... review the output of a deep-learning algorithm, correcting errors where applicable. The corrected results would then be fed back into the training set for the neural network, thus improving accuracy over time." 

## Problem

I had to solve serveral design problems inherent in this idea, while encountering issues arising from "scope creep" and keeping the interface clear and relatively easy to understand. The design of the page went through a multitude of iterations. The stakeholder wanted a visual representation of the percentages assigned by the AI, and I needed the solution to be dynamic to minimize the chance of coding errors in creating the representations. The images needed to be large enough to be recognizable to a user, yet small enough to not overwhelm other elements on the page.

## Solution

I chose to use Twitter-Bootstrap for the use of some of the default styles and for its grid system. I didn't want to have to stress about creating a grid for the "widget" layout in the meat of the interface, though I know I could create one. Bootstrap helped me maintain even spacing of the elements and kept the interface unified throughout the site.

Angular was very helpful, especially when displaying an iterating list of objects with unique data values, and needing to use those values to create the bar graph visual representation I created. I found a small image set to work with, and created the (fictional) AI values for some dummy data. (In practice, this data would be supplied by the backend developer.) 


## Conclusion

I attempted to begin the process of creating a function that would alter the data based on user input, but (with some mentor guidance) decided that ultimately that would be a backend issue and not one I should devote my time towards. A function call could very easily be added to the label/buttons on the image's interface, which would manipulate the data and allow for the values to be adjusted as needed.

There are other ways to display the AI data that would potentially tell the user more about the AI and the learning process. A frequency histogram (through a service/API such as D3 or google charts) would show a user the frequency that the different labels were selected for an image. 

I would conduct user research to decide if it was better to have the reclassified images disappear (to be reviewed at another time) or stay present in the view. It would be disorienting to users to have the image just disappear. However, should there be an opportunity for the user to change the error, or would the error be overwritten later as user-input eventually overpowers the fallacious input? This question in my mind is ultimately reserved for a conversation with the stakeholders and backend developers.

As the user descends in the dataset and the interface, how far would it go? Infinite scrolling [as tested very recently by Smashing Magazine](https://www.smashingmagazine.com/2016/03/pagination-infinite-scrolling-load-more-buttons/){:target="_blank"} is certainly not the answer, but a "load more" button would allow the user an exit, if needed.

Another matter that would depend on the size of the dataset would be how the page would react to the user leaving the page and/or refreshing the page. Would a completely new image set be available to the user, or would the user interact with the same dataset as before - and then how would the user ever get to the "end" of a very large dataset, if there were only 5-10 minutes available to use the application? These are questions, again, for the backend developer and stakeholders, and would necessitate some redesign.

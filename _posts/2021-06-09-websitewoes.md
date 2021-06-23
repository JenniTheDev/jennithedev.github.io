---
title: 'Website Woes'
date: 2021-06-09
permalink: /posts/2021/06/websitewoes/
tags:
  - problem solving
  - web dev
 
---

I decided to update the layout of my website so it would be easier for me to add stuff to it. I took a front-end web class, so it should be pretty easy to do, right? 

I'm somewhat convinced that anyone who makes webpages that work and look good is some sort of magician. I looked around and found a template that I liked, that didn't involve a lot of steps to rebuild every time I needed to write a blog post. After deciding that [AcademicPages](https://academicpages.github.io/) was perfect for what I wanted to do, I got to changing things around and making it my own. After I got it all set up, and a few blog posts copied over from my previous site, I proudly looked at my blog page and saw a post crammed in between two others: 

![](https://jennithe.dev/images/WebsiteWoes0.jpg)

That was not correct at all. I started trying to narrow down what could be causing the problem. All my blog posts were formatted the same using markdown. All the titles and headers were all the same format. The file names are all formatted the same. I tried deleting the file and creating a new one with just the header to see if it was something leftover from when I copied the blog post over. There was still no change. I tried making a test blog page to see if it had anything to do with the number of blog posts showing on the page, but the test posts worked perfectly. Then I noticed something in the address bar. 

![](https://jennithe.dev/images/WebsiteWoes1.JPG)
![](https://jennithe.dev/images/WebsiteWoes2.JPG)



The correctly formatted posts were all /posts/year/month/title. The incorrectly formatted one was /year-month-date-title. I then started trying to figure out why that one file was being formatted differently. I rubber duck'd with a friend to see if I was just tired and missing something. It's always helpful to get another set of eyes on a problem. After I was about to call it quits for the day I realized something. The problem post had an apostrophe in the title. None of my other posts had one. So to test my theory, I removed the apostrophe. It worked perfectly. I figured that since the title was enclosed in apostrophe's, that was the cause of my formatting problem.

I now know that if I am writing a blog post and want to use an apostrophe, I have to be sure to enclose it in quotation marks. 


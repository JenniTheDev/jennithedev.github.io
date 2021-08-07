---
title: 'Dearest Dictionaries'
date: 2021-08-06
permalink: /posts/2021/08/leetcodedictionary/
tags:
  - leetcode
  - problem solving
  
---

I’ve been trying to make it a habit to complete a LeetCode problem a day. In my tour of completing LeetCode problems, I’ve come to appreciate a certain data structure. 

What data structure is that? A dictionary. There are so many problems that can be solved by using a dictionary in some way. 

In the problem [Isomorphic Strings](https://leetcode.com/problems/isomorphic-strings/), two strings are isomorphic when all the letters in one string can be replaced to get the second string. One of the ways to do this is to create a dictionary of the letter pairs between the strings. If the dictionary contains the key already, and it’s value is a different letter, then you know the string isn’t isomorphic. If the dictionary contains the value and it doesn’t match the key you are checking, the string isn’t isomorphic. 

In the problem [Roman to Integer](https://leetcode.com/problems/roman-to-integer/), you must convert a roman numeral to an integer. The first thing I did was make a dictionary to hold the roman numeral symbol as the key, and the number value as the value. Then the rest of the conversion is just using the key to look up the value and then adding it up. 

Then we have the problem [Top K Frequent Words](https://leetcode.com/problems/top-k-frequent-words/). Adding an object to a dictionary and then checking if the key is there is a really easy way to see if you have duplicates of something. If you count how many times the object is not added, then you can know how many duplicates you have. 
 
There’s so many more problems that can use a dictionary to help solve them. I wasn’t aware of how useful a dictionary could be until I started practicing more problems. You can find my LeetCode practice solutions [here](https://github.com/JenniTheDev/LeetCode). 

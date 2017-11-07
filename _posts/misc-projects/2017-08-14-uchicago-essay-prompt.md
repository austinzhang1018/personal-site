---
layout: post
title: U-Chicago essay prompt fun
date: 2017-08-14
---
As a high school senior, I've started to look at some of the supplemental essays for different colleges, and one of U Chicago's prompts caught my eye. The prompt is, *"Due to a series of clerical errors, there is exactly one typo (an extra letter, a removed letter, or an altered letter) in the name of every department at the University of Chicago. Oops! Describe your new intended major. Why are you interested in it and what courses or areas of focus within it might you want to explore? Potential options include Commuter Science, Bromance Languages and Literatures, Pundamentals: Issues and Texts, Ant History..."* U Chicago is pretty well known for its unconventional prompts, and this prompt is no exception. However, this prompt was particularly interesting because there's a pretty cool project that can be adapted from it.

I couldn't think of many departments when I began brainstorming ideas for the essay, which led me to this project idea: an algorithm that scans all the possible word modifications for the majors. It should be a pretty simple project to brute force. For example, the word "Anthropology" is 12 letters long. For the word, you can choose to either insert a letter, delete a letter, or alter a letter. Since there are 12 letters, you have 12 letters to choose from to erase or alter and 13 slots where you could possibly insert a letter. This same pattern applies to all words, so each word has 3n+1 different possible modifications. However, in some of the modifications (inserting or replacing a letter), you also have to choose a letter you want to insert or replace, which adds to the complexity. There are 26 different letters you can insert, and 25 different letters you can replace the current letter with. this brings up the complexity by a large amount, so the total number of different combinations for a word of n length is 25n + 26(n+1) + n. This brings the number of combinations for our "Anthropology" example up to 650. This may seem like a lot of combinations to write out by hand, but it would take a computer less than a second to compute all of the combinations of not only the word Anthropology but of every word in all of the different majors at U Chicago.

Ok, enough background. Let's start coding.

Although there are a lot of different possible combinations, it's evident that most of them will be gibberish. That's why I'll want to cross check my combinations with an actual dictionary to see whether I have a real word or not. I downloaded a word list from [here](https://code.google.com/archive/p/dotnetperls-controls/downloads) that I'll use to see if my combination is a real word.

First I'll input the list into a set (for speed purposes, IO is very slow and it's horribly inefficient to scan the entire document every time I have a new word)

Now comes the fun part...permutating each word.

This part is actually very easy and can be accomplished with a couple while loops. After permutating the word, I check it against an English word list and if it's a real word, I store the result and original word in a key-map pair.

After all the different permutations have been tested I spit out the result map to a text document.

Now to actually see what words majors there were I had to type out all of the majors into a text document. This was definitely the worst part.

So once I finished writing the program, I ran it (runtime is < 1sec) and found that in total, with all the majors/concentrations/etc. listed on U Chicago's site, there are 663 different possible things you could write your topic on. This was actually a lot more than I expected, but keep in mind that the majority of these different possibilities are nonsensical.

As a closing note, although this program finds all the possible English permutations of the words in the U Chicago majors, it doesn't consider "punny" words to be real words (ex. Pundamentals). So we are assuredly missing out on a section of the possible prompts.
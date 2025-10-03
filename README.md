![alt text](https://github.com/gruquilla/FinAcNews/blob/main/Finacnews%20logo.jpg "Logo")
Academic paper fetcher and summariser for Fintech related topics.
<br />
<br />
📘 Access the FinAcNews Notebook: (To be published) 
<br />

## Table of contents
- [What is FinAcNews?](#what-is-finacnews)
- [Quick Preview](#quick-preview)
- [The project in detail](#the-project-in-detail)

## What is FinAcNews?
FinAcNews is a Python-based tool designed to fetch academic articles from a curated selection of reputable websites covering the FinTech sector. 
<br />
It automatically parses RSS feeds, filters the results using customisable keywords, and distils each article into a concise, plain-English summary, making complex research more accessible at a glance. Each summary comes with a link to access the full article online.
<br />
Users can tailor the script to define how far back in time it should search, which keywords trigger inclusion, and whether to display direct links to the original sources.
<br />

## Quick preview
<br />

## The project in detail
Here is how FinAcNews works:
* **Step 1: Configuration** <br />
  _In this part,the script defines customisable aspects of the research, such as the number of days of articles it should fetch and the keywords used for filtering articles._
<br />

* **Step 2: Summariser setup** <br />
  _After checking whether the system has a d-GPU, this part defines the function that will be used to summarise the articles using the BART model. Keep in mind: the script doesn't scrape anything, it just fetches the article academic summary and summarises it to make it more accessible. As a result, only the academic summary - and not the complete article- are summarised. However, this is more than often enough to give an overview to the user and let him decide wether or not he should check out the full article._
<br />

* **Step 3: Helpers** <br />
  _A series of functions that:_
  * Make sure the articles match the specified time window
  * Highlight in the summary the keywords having triggered the keyword-filter, mainly for debugging but also to make more visible the topics.
  * A way to extend the keyword list (eg: crypto -> cryptocurrency, cryptography, cryptos,...)
  * Adapt titles/ text to make them more readable on display (2 functions)
  * Filter the articles with the series of keywords prepared beforehand.
<br />

* **Step 4: Fetchers** <br />
  _This part fetches the articles from relevant fintech research websites, such as:_
    * Springer Open Financial Innovation journal
    * MDPI FinTech journal
    * Cryptology ePrint Archive
    * The Journal of Fintech (worldscientific.com)
    * ARXIV (q-fin and CS CR tipics)
    * IMF (Working papers, World Economic Outlook, International economic and financial papers). Not always relevant, but from time to time it's interesting to see what the IMF discusses about FinTech.
<br />

* **Step 5: Display** <br />
  _A function to display the articles by descending date in a customisable and interactive Plotly table._
<br />

* **Step 6: Main** <br />
  _Where everything finally happens: The block where the functions are called and the output displayed._
<br />

Code: © G.RUQUILLA - MIT License <br />

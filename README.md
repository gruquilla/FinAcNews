![alt text](https://github.com/gruquilla/FinAcNews/blob/main/Finacnews%20logo.jpg "Logo")
Academic paper fetcher and summariser for Fintech related topics powered by BART (HuggingFace Transformers library).
<br />
<br />
📘 Access the FinAcNews Notebook: <br />
[Open Version 1.4](https://github.com/gruquilla/FinAcNews/blob/main/FinAcNews%20V1.4.ipynb)
<br />

## Table of contents
- [What is FinAcNews?](#what-is-finacnews)
- [Quick Preview](#quick-preview)
- [The project in detail](#the-project-in-detail)

## What is FinAcNews?
FinAcNews is a modular Python pipeline that fetches, filters, and summarises academic FinTech research from leading journals and archives.
<br />

Designed for analysts, researchers, and enthusiasts, it transforms dense abstracts into digestible insights—complete with keyword highlighting, interactive tables, and full-source links.
<br />

## Quick preview
![alt text](https://github.com/gruquilla/FinAcNews/blob/main/preview.jpg "Script output preview")

## The project in detail
Here is how FinAcNews works:
* **Step 1: Configuration** <br />
  _In this part, the script defines customisable aspects of the research, such as the number of days of articles it should fetch and the keywords used for filtering articles._
<br />

* **Step 2: Summariser setup** <br />
  _After checking whether the system has a d-GPU, this part defines the function that will be used to summarise the articles using the BART model. Keep in mind: the script doesn't scrape anything, it just fetches the article academic summary and summarises it to make it more accessible. As a result, only the academic summary - and not the complete article- are summarised. However, this is more than often enough to give an overview to the user and let him decide wether or not he should check out the full article._
  
  _This project uses the Transformers library by Hugging Face to perform text summarization via the facebook/bart-large-cnn model. The model is licensed under the MIT License, and the implementation is made possible thanks to the Hugging Face team and contributors._

_Model reference: Lewis, M., Liu, Y., Goyal, N., Ghazvininejad, M., Mohamed, A., Levy, O., Stoyanov, V., & Zettlemoyer, L. (2020). BART: Denoising Sequence-to-Sequence Pre-training for Natural Language Generation, Translation, and Comprehension. Proceedings of the 58th Annual Meeting of the Association for Computational Linguistics. arXiv:1910.13461_

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
  
  _Note: This script does not scrape the data from the websites, and only fetches the publicly available data through RSS feeds. Full articles remain the intellectual property of their respective publishers and authors._

<br />

* **Step 5: Display** <br />
  _A function to display the articles by descending date in a customisable and interactive Plotly table._
<br />

* **Step 6: Main** <br />
  _Where everything finally happens: The block where the functions are called and the output displayed._
<br />

Code: © G.RUQUILLA - MIT License <br />

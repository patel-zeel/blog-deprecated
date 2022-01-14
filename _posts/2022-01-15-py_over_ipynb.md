---
toc: true
layout: post
description: Where .py files are better than .ipynb files?
categories: [markdown]
title: Why .py files are better than .ipynb files for ML codebase
---

I have made the shift from .ipynb files to .py files (and Jupyter to VS code) in the last couple of months. Here are some reasons why I feel .py files are better than .ipynb files:

## Less Errors
* .py files are easier to debug with a VS code like IDE which makes it easier to find the errors.
* Execution of .py starts fresh unlike some leftout variables silently getting carried over from the last execution/deleted cells in .ipynb files.

## Better Usage of a Shared Server
* .py files release the resources (e.g. GPU memory) once done executing. It could be inconvinient to repeatadelay remind someone or be reminded by someone to release the resources manually from a jupyter notebook.

## Increased Productivity
* You can make use of amazing auto-complete, syntax-highlighting extentions in VS code to save a lot of time while working with .py files.

## Boost Collaboration
* .py do not take time to render on GitHub because they are just plain text files unlike .ipynb files.
* It is a lot easier to see the changes made by others in a .py file compared to .ipynb file.

## Increased Modularity
* Function and Class calls from other files is seamless with .py files.

Feel free to comment your views/suggestions/additions in the comment box.

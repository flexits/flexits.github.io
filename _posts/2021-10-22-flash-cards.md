---
layout: post
title: "FlashCards – an app to learn words"
thumbnail: "/assets/flashcards.jpg"
categories: desktop
tags: [C#, Windows Forms, Dapper, SQLite]
excerpt_separator: <!--more-->
---

![FlashCards screenshot](/assets/flashcards.jpg)

A simple application designed to assist with memorizing foreign words. It’s based on the well-known concept of flashcards, where one side displays a foreign word and the other side shows its translation. Each card can also include a picture, and the cards can be organized into stacks (for example, by relevance to a certain topic). The stacks can be imported and exported, making it easy to share or transfer your learning materials. The app features a multilingual user interface (English and Russian are currently supported).

<!--more-->

## Technical

This is a Windows Forms app, but it's styled in a slightly fancier way. Inheritance is used extensively to prevent code duplication in the forms and custom controls.

Localization strings are stored in resources and accessed via ResourceManager. The cards are stored in an SQLite database that is object-mapped by *Dapper*. Import/export is done through plain text JSON files with a custom extension. The color palette was chosen with help of *[Coolors](https://coolors.co/)*.

This is an example of my early coding and contains certain errors in both architecture and implementation, I believe. The project structure itself is messy too (models, database access layer, localization service – everything resides in the root folder).

### Sudden discovery

Visual Studio's Designer doesn't work properly when a form is inherited from a base class. Seems to be an [ongoing issue](https://developercommunity.visualstudio.com/t/VS-2022-WinForm-Designer-not-working-wit/1581567) still.

## Project link

<a href="https://github.com/flexits/FlashCards" target="_blank">
  <i class="fab fa-github fa-2x" title="View on GitHub"></i>
</a>

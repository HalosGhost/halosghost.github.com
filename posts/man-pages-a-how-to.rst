.. date: 2013/07/20 10:39:54
.. description: 
.. tags: 
.. link: 
.. slug: man-pages-a-how-to
.. title: Man Pages, a How-to
.. nocomments: True

One of the projects I have come to work with the most during my tenure using Arch Linux is `Alopex <https://github.com/TrilbyWhite/alopex.git>`_. It is an extremely lightweight Window Manager (~1500 sloc, with no edits). It is, in many ways, similar to `dwm <http://dwm.suckless.org/>`_. Like dwm, Alopex is written entirely in C and, as a result, essentially all its configuration options (of which there are plenty) are sourced at compile time. This leads to the whole window manager being in the neighborhood of 70 KiB (74 with all my customizations). When I first became interested in Alopex, the only documentation available was the generously-commented ``config.h`` (the file inside which almost all user customizations reside). Partially to help contribute to this project as best I could, and partially to get comfortable editing and contributing to the (fabulous) `ArchWiki <https://wiki.archlinux.org>`_, I created `Alopex's ArchWiki page <https://wiki.archlinux.org/index.php/Alopex>`_. This, I would like to think, is a very helpful resource (particularly for Arch users). But, much of it is very focused on Arch Linux alone, and since Alopex is not a project explicitly meant for Arch (though all of its contributors are Arch users at the moment), I wanted to help provide documentation that would benefit anyone that might use Alopex.

Thus, I began looking into writing man pages. For anyone who isn't aware, ``man`` is a utility for reading "manual" pages provided by upstream projects. The ArchWiki might be nice, but it can be edited by anyone and there is no guarantee that it will stay up-to-date. Man pages, on the other hand, come directly from upstream (or from dedicated contributors), so they should always be the first source to consult. To accurately document Alopex, I felt I needed to create three pages.

#. `alopex.1 <https://github.com/TrilbyWhite/alopex/blob/master/alopex.1>`_
#. `alopex.icons.5 <https://github.com/TrilbyWhite/alopex/blob/master/alopex.icons.5>`_
#. `alopex.config.5 <https://github.com/TrilbyWhite/alopex/blob/master/alopex.config.5>`_

The first is a simple and relatively short page that gives a very wide and concise overview of what Alopex is. The second is an even shorter page documenting how Alopex creates its icons and giving some guidance on how a user might add their own custom icons. In the future, the icons page might become a themes page and also include documentation on Alopex's color-schemes. And, the final page is a much larger page which documents, in-depth, all the features of the ``config.h``.

Man pages are written in a language called groff, but for the most part, they are just plain-text with various formatting modifiers to reflect convention. The basic modifiers you'll need to know to setup the most basic of man pages are as follows:

+-----+--------------------------+
| .TH | Creates the Page Header  |   
+-----+--------------------------+
| .SH | Creates a Section Header |
+-----+--------------------------+
| .RS | Indents following text   |
+-----+--------------------------+
| .RE | Dedents following text   |
+-----+--------------------------+

While there are conventions for formatting various things (bold for commands and environment variables, italic for files, etc.), these are largely up to the man page author (though you should make sure that you're use of formatting is consistent throughout your writing, and following convention is a good idea). There are also various ways to format text, there are simple modifiers like ``.TH`` and ``.SH`` which will only affect text that follows on the same line, and there are also more complex modifiers that allow you to add them in-line to a paragraph. Personally, I tend to prefer the in-line versions so I do not have to deal with the disjointed nature of all the extra line-breaks.

For a fabulous, in-depth walk-through of everything you could ever want to know about man pages, take a look at this `page <http://www.schweikhardt.net/man_page_howto.html>`_ by Jens Schweikhardt. And feel free to take a look at the pages I wrote and linked to above and use them as a starting point for your own projects.

---
title: "Me, a millennial, learning Vim from scratch"
date: 2019-07-24T19:26:00+04:00
draft: false
tags: ["Vim"]
slug: "English Preview"
---

{{< figure src="/images/exit-vim.jpg" >}}

If you are like me, you probably asked yourself "How to exit Vim?"
at some point in your life. 

<br>
So you probably have tried hitting that Esc, it doesn't work.

Ok what about the good old Ctrl + C... it doesn't respond.

Type quit + enter? Well, it does type "quit" with a new line 😅

<br>
It turns out that this is a common question, because literally over [one million developers](https://stackoverflow.blog/2017/05/23/stack-overflow-helping-one-million-developers-exit-vim/) have asked this question! Good to know that we are part of this global developer confusion right?

## So how did I start learning it?

I had the same confusion for the first 21 years of my life. Until
one day my CTO Alex at Namshi sat down and shed light on my situation as he watched
me struggle in the terminal trying to find a word in Vim with my down down down down
down down down down down down down down down keystrokes.

> Just open your terminal and type vimtutor. You will get an interactive tutorial to learn Vim

What? Learning Vim? The ancient mythical thing that no one uses?

These are the first
thoughts that ran through my head, but as an adventurous developer, I decided to
give it a try. So after work that day, I pulled out my laptop and started
vimtutor on my dark/green terminal. Starting from Lesson 1,
I learned how to move my cursors with hjkl,
how to quit Vim, how to delete, edit, and insert texts, etc. 
As I went half-way through the tutorial, my mind was going half
crazy... I got to admit trying to map a keydown to an
action in a text editor was not a common job for my brain 😅

<br>
How does `fp c2w` make any sense anyways?

<br>
As I went down this rabbit hole, I decided to look for
some resources to help me memorize Vim commands. There are tons
of Vim resources online, some for beginners,
and others for absolute [Ninjas](https://www.vimgolf.com/).
I tried almost all the free Vim learning resources online,
and I want to share the ones I find useful.

## What resources did I find useful to learn Vim?
### [vim-adventures](https://vim-adventures.com/)

Vim adventures is an interactive game with beautiful UI that teaches you Vim.
As I was starting off, trying to remember `hjkl` to move the cursor was very challenging.
Vim adventures really helped me build muscle memory as I had to use them to get the key and open treasure boxes. The first few sections of the game are free, and the remaining ones are paid.
Nevertheless, it is a very entertaining and educational game.
{{< figure src="/images/vim-adventures.jpeg" >}}

### [Oni](https://github.com/onivim/oni)

Oni is a modern modal editing software powered by Neovim. I find its interactive
tutorial fun and helpful. It has amazing UI and teaches you
commands by asking you to complete certain goals. For example, a goal might be 
`Use 'G' to move to the BOTTOM of the file`, etc. It simulates a real
world experience of using vim to edit texts. You can see and experience
what is the use case and benefit of each command. When you finish a challenge,
it also shows you how many keystrokes and how much time it takes to finish it.
So you can have a benchmark, come back and practice more to see the progress.
After completing all the tutorials on Oni, I could easily use the basic Vim commands,
and even something more advanced like `ci(` or `da{` etc.

{{< figure src="/images/oni.gif" >}}


## What other tools did I discover?
### [Vundle](https://github.com/VundleVim/Vundle.vim)
[Vundle](https://github.com/VundleVim/Vundle.vim) is the plugin manager for Vim. Vundle makes it very easy to install language
specific plugins and other configurations such as themes. Its github page also has an [examples page](https://github.com/VundleVim/Vundle.vim/wiki/Examples) of people's configurations, from which I copy-pasted and happily used so far.

## What do I think about Vim now?
After learning Vim last year and using it everyday since, my view of Vim has shifted from the struggle and confusion to embrace and understanding.
It becomes really fast and handy for some specific text editing jobs. For example, when I squash commits with git, I don't need to change each `pick` to `s` anymore. I just need a simple `:2,10s/pick/s/g`
and that substitutes the text to exactly what I want. I really appreciate how the creators of Vim made such a beautiful and productive tool and designed its flexibility to solve different sorts of tasks.

If you haven't tried Vim or just start learning it, I hope this post helps you a little bit. If you are  a Vim guru, let's compete with some [Ninja-level](https://www.vimgolf.com/) challenges ⚔😆

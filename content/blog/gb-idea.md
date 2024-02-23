+++
template = 'custom/blog-post.html'

title = 'My idea about the guestbook'
description = 'The best way to create a guestbook in a static html project'
date = '2024-01-12'
slug = 'gb-idea'
year = 2024
month = 1
day = 12
lang = 'en'

[extra]
author = 'b1ek <me@blek.codes>'
+++

# In short...
You might know that my website [used to have a guestbook](https://old-1.blek.codes/guestbook) (at the moment of writing this article), and it was relatively easy to implement since the whole thing used to run on express.js and a bunch of databases.

# The problem

Thing is, the current version of the website (the one you are browsing right now) is written in [Zola](https://getzola.org), which compiles into a bunch of static .HTML files.
This is obviously good in terms of server costs and performance, but isn't very good when you need to add interactive shit like guestbooks, statistics and stuff.

I mean, I could've chosen literally any other framework when i was doing the rewrite - SvelteKit, Rust+Warp, hell, even Laravel: basically anything that supports server side HTML rendering. But i kinda want to do this one completely static.

# Possible solutions
Well, the first one and the most obvious one is to not to have a guestbook. It is pretty hard to filter out the spam and overall its kind of not worth the trouble.

However, i still want for y'all to leave a message here so im jumping to solution 2: Create a separate docker service or smth that handles POST forms and serves the data.

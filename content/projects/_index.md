+++
title = 'Projects'
+++

<link href='/dropdown.css' rel='stylesheet'>

## Preamble
I love doing weird ass shit. Almost none of these projects are completely finished and are ready for production deployment, but have fun!

Also note that this page does not include any of the commercial projects I was part of.

## CSV list in case you want to parse it
<a href='#csv-list'>click to show</a>
<div class='dropdown' id='csv-list'>
    <pre>
name,link,license,discounted
blek! File,https://file.blek.codes,GPL-3.0-only,false
blek! World,https://blek.codes,GPL-3.0-only,false
blek! Bin,https://bin.blek.codes,GPL-3.0-only,false
blek! EOL,https://eol.blek.codes,PRIVATE,false
blek! Sail,https://github.com/b1ek/sail,NONE,false
blek! Wordle,https://wordle.blek.codes,NONE,false
blek! ID,https://github.com/b1ek/blekID,true
VRPLauncher,https://github.com/b1ek/VRPLauncher,false
win7sim,https://github.com/b1ek/win7-sim,NONE,false
    </pre>
</div>

# The List

### 1. blek! File 🌠
It is supposed to be a file sharing platform, like [`0x0.st`](https://0x0.st), but with a funny GUI & extended functionality.

My instance is running [here](https://file.blek.codes). Check the [git repo](https://git.blek.codes/blek/bfile) for other instances.

It is built on Rust and [Warp](https://github.com/seanmonstar/warp) and is divided onto a lot of microservices which are managed via docker-compose.

### 2. blek! World
Its this website!! It is actually a redesign of the old version which i think i might keep [here](https://old-1.blek.codes) (expect this link to be dead). You can also check out the archive.org archived copies.

It is built on [zola](https://getzola.org), which generates static .HTML files you can put anywhere.

### 3. blek! Bin
A simple ass pastebin copy. Also has a funny HTML-only captcha that has not been cracked so far.

It is built on express and stores data in simple files.

### 4. blek! EOL
The super secret letter and a website that will be displayed in the case of my death. Don't tell anyone, ok?

It works by pinging all my devices each hour and prompting me to enter a 6-digit PIN code to tell the service i am still alive. If i enter the code wrong, it assumes i am dead and someone tries to pick the code.

### 5. blek! Sail
If you use laravel you know a development tool called Laravel Sail.

This one is a single docker container that runs your laravel app with production optimizations.

It is built on a bunch of shell scripts and dockerfiles.

### 6. blek! Wordle
A FOSS copy of the [wordle game](https://www.nytimes.com/games/wordle/index.html).

Built with Svelte.

### 7. blek! ID
My own implementation of an SSO. It is supposed to be OAuth2 compatible, but then i learned that OIDC exists so i abandoned this project. It is written in Laravel and PHP8.

### 8. VRPLauncher
A minecraft launcher for my server. It has custom license which will in no way survive in court and is built on WinForms of all things.

It does its job, though. Like, it has been written before microsoft accounts for minecraft so you probably couldn't log in, but you can run minecraft from it.

It also relies upon [this library](https://github.com/CmlLib/CmlLib.Core) to manage all the launcher stuff.

### 9. Windows 7 simulator
I built this for fun using the most horrible web practices one could think of.

Have fun going through the [github repo](https://github.com/b1ek/win7-sim) if you want to waste some of your time.
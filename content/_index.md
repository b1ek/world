+++
title = "Welcome"
+++

## Welcome to my world!
Hello there! My name is Alice and i am a fullstack web dev. I like to start a lot of side projects, but finish only a few of them.

## My contacts
You can send me an email (preferred): [me@blek.codes](mailto:me@blek.codes)  
I can also be reached via [telegram](https://t.me/bleki42).

<div class='js-only'>
    My time in my timezone is: <span id='time'></span>
    <script>
        (async () => {
            function update() {
                document.getElementById('time').innerText = new Date(
                    new Date().toLocaleString('en-US', { timeZone: 'Asia/Vladivostok' })
                ).toLocaleString('en-US', {
                    hour: 'numeric',
                    minute: 'numeric',
                    second: 'numeric',
                    hourCycle: 'h24'
                });
                setTimeout(update, 1000);
            }
            update()
        })()
    </script>
</div>

I also made a lil badge to show if i am currently online. Cool, huh?  
<img src='https://online.blek.codes/gif' height='31px' width='88px' alt='A badge showing if i am online or not. Sorry, the only way to know it is to load the gif. It would be all greeny if i am online' />  
<a href='/online-badge'>how does it work?</a>

## Projects
You can find the list of my projects [here](/projects).

## Webrings!!
I like webrings.

<a href="https://webring.haaien.xyz/#1" target="_blank" rel="noopener"><img src="/hairing.gif" alt="A button saying haaien webring" height='31px' width='88px'/></a>
<a href="https://acingtheinternet.netlify.app" target="_blank" rel="noopener"><img src="/acenow.gif" alt="A button saying asexuals now" height='31px' width='88px'></a>

---

### World's thoughts

Did you ever wonder what a [caterpillar](/caterpillar) looks like?
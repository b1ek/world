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

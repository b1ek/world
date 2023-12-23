+++
title = 'It is over'
+++

<style>
    @keyframes over-fade-in {
        0% {
            opacity: 0;
            transform: translateY(-50%);
            filteR: blur(24px)
        }
        to {
            opacity: 1;
            transform: translateY(0%);
            filteR: blur(0px)
        }
    }
    .over {
        text-transform: uppercase;
        font-size: 5em;
        font-weight: 900;
        font-family: 'Open Sans', 'Segoe UI', 'Verdana', sans-serif;
        text-align: center;

        animation: over-fade-in 2s ease;
        animation-fill-mode: forwards;
        animation-delay: 1s !important;

        opacity: 0;
        color: #a0a0a0;
    }

    .not {
        width: 0px;
        display: inline-block;
        clip-path: inset(0 0 0 0);
        transition: 250ms ease;
        text-decoration: none;
        color: white;
        text-align: center
    }
    .not:visited {
        color: white
    }

    .over:hover > .not {
        width: 240px;
    }

    #tip {
        position: fixed; z-index: 10;
        top: 50%; left: 50%;
        height: 300px;
        transform: translate(-50%, -70%);

        background: #ffffff02;
        backdrop-filter: blur(32px);
        padding: 40px;
        border: 1px solid #c2c4c220;
        border-radius: 20px;
        
        opacity: 0;
        filter: blur(24px);
        transition: 250ms ease;

        display: flex;
        align-items: center;
        pointer-events: none;
    }
    #tip:target {
        opacity: 1;
        filter: blur(0px);
        transform: translate(-50%, -50%);
        pointer-events: all;
    }
</style>

<div id='tip'>
    Just go back to the previous page. duh
</div>

<p class='over'>
    It is<a href='#tip' class='not'>&nbsp;NOT!</a> over.
</p>
<p class='over' style='font-size:2em;text-transform:none;animation-delay:2s !important;font-weight:normal'>
    You have died while traveling through the blek! World.
</p>
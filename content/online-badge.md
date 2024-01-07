+++
title = 'The funny badge'
+++

It is actually dead simple: there is a simple server running on `online.blek.codes` and a cron job on my laptop that sends POST requests every minute (a heartbeat protocol basically) and that server serves that gif on URL `online.blek.codes/gif`.

If the server didn't receive a heartbeat for a few minutes, it assumes that i am offline and serves the offline gif.

You can [add it to your website too](http://git.blek.codes/blek/online.git), but it will require a bit of tinkering and requires you to have a web server as well.
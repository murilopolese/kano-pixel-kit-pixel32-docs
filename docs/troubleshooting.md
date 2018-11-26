---
layout: documentation
---

# Troubleshooting

## I tried everything on this page but my problem persists, please send help!

Don't lose your hopes, if your problem persists or you have a question that is not answered here or by the [documentation]({{ '/documentation' | relative_url }}), please open a [Github issue](#github-issues)!

## I'm trying to flash my Pixel Kit using the Flash Tool but no "serial port" is listed there.

There are 2 things that might be causing this issue: Drivers and the serial connection between the Pixel Kit and your computer.

To install the drivers, there are a few options but the safest one is to download and install the [Kano App for Pixel Kit](https://kano.me/app). If you don't want to install the Kano App you can manually install the [FTDI drivers](https://www.ftdichip.com/Drivers/D2XX.htm).

If your drivers are installed, it could be something with the communication between the Pixel Kit and your computer. Make sure your Pixel Kit is turned on and the USB cable is connected both to your computer and Pixel Kit. The USB cable must be a "data enabled" cable like the red one that comes in the box.

If after following this instructions you still can't flash your Pixel Kit, please write about it on the [Github issues](https://github.com/murilopolese/kano-pixel-kit-flash-tool/issues) telling what OS and the version of Pixel Kit Flash Tool you are using.


## I'm losing connection all the time!

If you are losing connection while on the "blue screen" that might be that your OS doesn't like very much the way Pixel Kit creates wifi networks. Make sure your Pixel Kit is charged or charging and close to your computer, both low battery and the smallest barrier between your computer and the Pixel Kit can make a big difference.

If the problem persists, try connecting both your computer and Pixel Kit to an available wifi network as it tends to be more stable and a bit more reliable.

If you are losing connection all the time on the green screen, try to get closer to the wifi router you are connecting to.


## How can I find the name of my Pixel Kit network on the blue screen?

If your Pixel Kit is showing the blue screen, it's connected for sure to a network named something like `PIXEL_KIT_XXXXX`, where the `XXXXX` is a bunch of numbers. Each Pixel Kit has a unique number and the best way to find out this number is to turning off all the Pixel Kits (except the one you are examinating) and check what is the only Pixel Kit network that appears. If you have many Pixel Kits, it could be nice to write or put a sticker with this number on them.


## How can I find what network my Pixel Kit is connected to?

If you are able to connect to your Pixel Kit by its ip address it means it's connected on the same network as your computer. But if you can't connect to your Pixel Kit, the best way to find out what network it is connected, or trying to connect, is to force the "blue screen" (turn it off and on again pressing both red buttons on the bottom right). Once that is done, connect the terminal page to to your Pixel Kit and type on the REPL:

```
>>> CONF.SSID
```

That will print out the network name it's connected (or trying to).


## My terminal page won't load / loads partially

If you are loding the page using the Pixel Kit ip address, please click on the download button to save and open it locally. Although Pixel Kit can host web pages, it's not the fastest in the world doing that. Opening from your computer is the best way to do it.

If you are opening from your computer, make sure you have downloaded the page correctly by waiting until the end of the download. If the problem persists, try downloading it again. Sometimes you can cancel the download without realising it and the page won't load properly.


## I can open the terminal page but can't connect to Pixel Kit

Make sure your Pixel Kit is turned on and your computer is connected to the same wifi network as your Pixel Kit. If you have made it already, make sure you are not opening the "terminal page" under the `https` protocol: If you are opening [the live terminal page](http://murilopolese.github.io/kano-pixel-kit-pixel32-docs/live/) or using the ip address (like `http://192.168.4.1`) make sure it's `http://` and not `https://` before the address.


## My terminal page is stuck, I can't run code or type on the REPL

You are probably disconnected. Reload the page and reconnect the terminal page to the Pixel Kit. Sometimes you will need to restart your Pixel Kit as well.

**Tip 1**: Refreshing your terminal page when it's being opened from your computer takes less than a second!

**Tip 2**: By pressing the "up arrow" on the terminal you can navigate previously typed commands. Notice that the "disconnected" history is different from the "connected" history.


## My terminal is stuck prompting `...` instead of `>>>`

This is something to do with the MicroPython REPL. Whenever it prompts `> > >` it means it's waiting for new instructions. Python instructions can have many lines, like a `for` loop, a function definition with `def` or an `if` statement.

The way the REPL tells you that it's processing a multiline instruction is by prompting a `. . .`. So for a `for` statement on the REPL it would be something like this:

```python
>>> for i in range(0, 5):
...     print(i)
...
...
...
0
1
2
3
4
>>>
```

Notice you have to press enter quite a few times for the code to execute. If you want to give up on your multiline instruction and just go back to the regular REPL, press `CONTROL + C`.

Learn more about it from the [official python documentation](https://docs.python.org/3/tutorial/interpreter.html#interactive-mode).

**Tip**: It's much better to use the code editor to run multiline instructions.


## My Pixel Kit stops working and it's not a problem with the terminal page, how can I "debug" it?

Try connecting your Pixel Kit via cable and creating a [Github issue](#github-issues) with that log.


## How can I connect to the Pixel Kit via cable?

Yes! And usually connecting via cable is much more reliable than via USB but you will be moving out of Pixel32 realms to do it, which is great! There are many other ways to interact with your Pixel Kit and you should definitely explore and find which one is the best for you. It might be that you started with Pixel32 but now it's time to level up.

So here are a few ways you can connect via cable to your Pixel Kit:

- Follow [MicroPython's official instruction](https://docs.micropython.org/en/latest/esp8266/tutorial/repl.html#repl-over-the-serial-port)
- Follow [Adafruit's amazing tutorial](https://learn.adafruit.com/micropython-basics-how-to-load-micropython-on-a-board/serial-terminal)
- Check the [Programs, Libraries and Tools section on MicroPython's forum](https://forum.micropython.org/viewforum.php?f=15&sid=caaabb0449bd1ced299db20e5213690e)
- Try [Flying Circus](http://flying-circus-ide.herokuapp.com/)


<div id="github-issues"></div>
## How can I open a Github Issue?

Please read carefully this page to see if there is anything you are missing out, sometimes small details makes all the difference. But if you are having a real hard time, don't hesitate to open a [Github issue](https://github.com/murilopolese/kano-pixel-kit-pixel32/issues) with:

- What OS and browser are you using (with version)?
- What were you trying to do?
- What did you expect to happen?
- What happened?
- Screenshots if possible.
- Error logs if any.


## How can I see the "error logs" from my terminal page?

The page "logs" are printed on the Javascript console of your browser. To open the console you usually right click with the mouse on the page and select "inspect" or "inspect element". It will split or open a new window with the "developer tools". On the "developer tools" there should be written "console" somewhere with the logs and possible javascript errors: That is the most valuable information to help fixing the bug. Something like [this](https://developers.google.com/web/tools/chrome-devtools/console/images/console-panel.png)


## I have a question that is not here, how can I add?

First open a [Github issue](#github-issues) and we'll discuss an answer and perhaps a solution for your problem there. Once we are all happy about it and if it's a popular question, we can write it down here. Deal?

<br>
<br>
<br>
<br>
<br>
<br>

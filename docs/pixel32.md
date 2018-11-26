---
layout: documentation
---
# Connecting to Pixel32 terminal page

## Ip Address

When your Pixel Kit is connected to a wifi network it will display its ip address in binary format. Red dots mean 1, no dots mean 0.

Make sure your Pixel Kit and computer are on the same network (either the one Pixel Kit created itself or the one you connected it to) and type the ip address in binary or decimal format. It will look something like this:

```python
> 11000000101010000000010000000001
```
or
```python
> 192.168.4.1
```

## Boot screens

When your Pixel Kit boots up it shows a few screens to let you know what it's doing and its state. Here is what they mean:

- Orange: Trying to connect.
- Blue: Created its own wifi network. It should be named something like PIXEL_KIT_XXXX but with a number instead of the XXXX.
- Green: Connected to a wifi network.
- Red: Tried to connect to a wifi network and failed.

## Blue Screen

The blue screen is a very special screen as it will allow you to connect to your Pixel Kit anywhere, without cables, with or without internet or available wifi networks.

The first time your Pixel Kit boots it will always display the blue screen. The Pixel Kit ip address while displaying the blue screen will never change: it will always be `192.168.4.1`.

At any time, turn your Pixel Kit off and on again while holding both red buttons to gently force it to show the blue screen.

This is very useful if you have connected to the wrong wifi network, one that is not available anymore, to code offline or to connect to a new network.

## Connecting to a wifi network

While connected on the network created by the Pixel Kit you won't have access to internet. If you want to code and have access to internet you must connect the Pixel Kit to a wifi network that has internet. The computer you will use to code must be connected to the same network.

The easiest way to connect is to run `saveWifiConf(ssid, passord)` on the REPL where `ssid` is the name of the network you want your Pixel Kit to connect and `password` is the network password.  Something like this:

```python
saveWifiConf('KanoGuest', 'everyonecanmake')
```

This will save this information on a file called `wifi.py` that is used by Pixel Kit on boot. After running `saveWifiConf(ssid, password)`, you must turn your Pixel Kit off and on again to apply the changes.

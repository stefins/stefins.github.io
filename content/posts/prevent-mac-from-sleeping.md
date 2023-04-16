+++
title = "Prevent Mac from sleeping even with closed lid."
date = "2022-05-25"
menu = "main"
+++

In this tutorial I'll show you how to prevent your Mac from sleeping 
without using any external tools

Open `Terminal`

Type 
```sh
$ sudo pmset -a disablesleep 1
```
This will prevent the Mac from sleeping

Now you can work with your Mac with closed lid. (I'm doing rn)

To turn back sleeping just type
```sh
$ sudo pmset -a disablesleep 0
```

Thanks :)
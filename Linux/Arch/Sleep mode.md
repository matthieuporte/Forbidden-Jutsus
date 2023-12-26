
There is different kinds of sleep mode. 
When you suspend your laptop, two modes are available : `s2idle` and `deep`. 

You can see which is activated with :
```shell
cat /sys/power/mem_sleep
```

`s2idle` is a state that is pretty much the computer just doing nothing but not essentially saving battery. It allows a very quick resume of activity.

`deep` on the other hand is the s3 state which is suspend to ram. There will still need to be some amount of power but only what's necessary to keep the ram alive. 

You can see when your computer has been suspended and woken up with :
```shell
sudo journalctl | grep "PM: suspend" | tail
```

If you want to change your sleep mode you can set it up temporarily with :
```shell
echo "deep" > /sys/power/mem_sleep
```

or definitely with :
```shell
sudo vim /boot/loader/entries/arch.conf
```
then add `mem_sleep_default=deep` at the end of the option line.
# Welcome to Linux!

## First Step towards Linux
Since I have heard tons of flowery words about how good the linux is and had enough of the hostility of developers towards Windows user, I decided to learn linux. Ubuntu is among the top of the list of my selection. My roommate, my classmates, my friends, almost everyone I have met chose Ubuntu as their OS. So do I. May you the best luck, Mr. Huang, the new developer!

## Install Ubuntu alongside the Windows 10
Both of two OS are awesome so I decided to abort none of them. I did a lot of homework about how to install two OS on one PC; I have to admit that I am not very good at the fundament of the computer and the operating system. Finally I realize that as long as I correctly settle the BOOTSTRAP file, both of the OS would load successfully. I referred to this [blog](https://www.jianshu.com/p/16b36b912b02) and installed the 2nd OS.

## Time conflict
Windows and Ubuntu are based on separate time setting. I referred to this [blog](https://www.cnblogs.com/qf19910623/p/5559514.html
) to handle this conflict problem.

```
sudo apt-get install ntpdate
sudo ntpdate time.windows.com
sudo hwclock --localtime --systohc
```


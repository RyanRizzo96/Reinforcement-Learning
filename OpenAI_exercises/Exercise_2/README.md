# 12/03/19 - Installing MuJoCo 

 1. Download the MuJoCo version 1.50 binaries for Linux, OSX, or
    Windows.
 2. Unzip the downloaded mjpro150 directory into ~/.mujoco/mjpro150, and
    place your license key (the mjkey.txt file from your email) at
    ~/.mujoco/mjkey.txt
 3. export
    LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/home/root/.mujoco/mjpro150/bin
 4. pip3 install gym[mujoco]


**Test Installation:**

    root@Linux:~$ pip3 list | ag mujoco-py

> mujoco-py                          1.50.1.68

    root@Linux:~$ pip3 list | ag gym

> gym                                0.11.0

    root@Linux:~$ python3

> Python 3.6.5 |Anaconda, Inc.| (default, Apr 29 2018, 16:14:56)  [GCC
> 7.2.0] on linux Type "help", "copyright", "credits" or "license" for more information.

    import gym
    env = gym.make('HandManipulateBlock-v0')
    env.reset()

> {'observation': array([-1.74609702e-01, -1.90536121e-01,  . .
>         0.2618407 , -0.3009019 ])}

    env.render()

# BlueICE Client Environment Setup
This repository contains instructions and files to set up the client side environment to operate with BlueICE server over the network (remote communication). The motivation behind this is that the initial effort to set up the client following the instructions form the [official documentation](https://carla.readthedocs.io/en/0.9.15/start_quickstart/) and connect to the server failed with the following error for some client scripts, such as the following:
``` bash
$ python3 manual_control.py --host <server-ip>
...
Traceback (most recent call last):
  File "./manual_control.py", line 1383, in <module>
    main()
  File "./manual_control.py", line 1375, in main
    game_loop(args)
  File "./manual_control.py", line 1272, in game_loop
    world = World(sim_world, hud, args)
  File "./manual_control.py", line 218, in __init__
    self.restart()
  File "./manual_control.py", line 288, in restart
    self.collision_sensor = CollisionSensor(self.player, self.hud)
  File "./manual_control.py", line 888, in __init__
    self.sensor = world.spawn_actor(bp, carla.Transform(), attach_to=self._parent)
RuntimeError: rpc::rpc_error during call in function spawn_actor_with_parent
```
Use the environment configuratoin files as below, and it is highly recommended to use a virtual environement manager such as conda. This was tested with Python 3.10, and it is assumed that you have already installed if you choose to use requirements.txt:

``` bash
conda env create --file environment.yml
pip3 install carla-0.9.15-cp310-cp10-linux_x86_64.whl
```

You should also clone [CARLA simulator repository](https://github.com/carla-simulator/carla/) to access the client scripts (carla/PythonAPI).

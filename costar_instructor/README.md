# Instructor

This is a package for creating and saving robot behaviors using a user interface for behavior trees.  This code also includes support for maintaining workspace waypoints, as well as a series of plugins for different robot capabilities.  Right now these plugins are geared towards different operations of the UR5 and LBR robots.

If you find this code useful, please cite:
```
@article{paxton2016costar,
  title={CoSTAR: Instructing Collaborative Robots with Behavior Trees and Vision},
  author={Paxton, Chris and Hundt, Andrew and Jonathan, Felix and Guerin, Kelleher and Hager, Gregory D},
  journal={arXiv preprint arXiv:1611.06145},
  year={2016}
}
```

## Adding plugins

Make sure you setup `instructor_plugins/src/instructor_plugins/__init__.py` to load your ui element.
Also add your ui element in
`costar_instructor/instructor_plugins/package.xml`. Take a look at the `case` entry, it will determine whether your plugin will be enabled/disabled under certain instructor roslaunch

For example if a plugin should appear in all cases, it makes sense to put `baseline` as your case.

## Marlin Demo

```roslaunch instructor_core marlin_cameras.launch```

Or:

```roslaunch instructor_core dual_cameras.launch
roslaunch instructor_core dual_alvar.launch
roslaunch instructor_core semi_static.launch
```
Then:
```roslaunch ur_driver test_servo_driver.launch robot_ip:=192.168.1.155
roslaunch robotiq_c_model_control CModelTeleop.launch 
rosrun rqt_gui rqt_gui
```

## CoSTAR Demo

Requires the __costar_stack__ repository.

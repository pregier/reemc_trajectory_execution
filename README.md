## General Info

This catkin package provides a ROS service to execute footsteps for the REEM-C simualation which can be found [here](https://github.com/philkark/hrl_reemc_forks).

## Services

The first service can be found under the topic *execute_single_footstep* and has the following settings:

* foot. A uint8 to defines the swing foot. The type should be set via the constants *left* and *right* from the service request type.
* footstep_x, footstep_y, footstep_z, footstep_yaw. They define the desired pose relative to the support foot.
* footstep_height. The height of the stepping motion, which is defined as **max('initial foot z','final foot z') + footstep_height**.
* footstep_duration. The duration (in *s*) for moving the footstep from the initial to the goal pose.
* base_height. The height of the base above the support foot.
* base_speed. The speed (in *m/s*) at which the base moves to lie above the support foot.

The second service can be found under the topic *step_to_init_pose* and has the following settings:

* support. A uint8 to defines the swing foot. The type should be set via the constants *left* and *right* from the service request type.
* footstep_duration. The duration (in *s*) for moving the footstep from the initial to the goal pose.
* foot_separation. The separation of the feet after performing the step.
* base_height. The height of the base above the support foot.
* base_speed. The speed (in *m/s*) at which the base moves to lie above the support foot.

## Topics

The node additionally provides information about the current state of the motion execution and publishes the current state to the topic *busy_executing_step*.

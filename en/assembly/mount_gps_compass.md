# Mounting a Compass (or GNSS/Compass)

External compasses, including combined GNSS/Compass hardware, should be mounted on the frame as far away from other electronics as possible, preferrably with the direction marker pointing towards the front of the vehicle (this is the default orientation).

The diagram below shows the heading marker on the Pixhawk 4 flight controller and compass.

![Connect compass/GPS to Pixhawk 4](../../assets/flight_controller/pixhawk4/pixhawk4_compass_gps.jpg)

## Compass Orientation

If you can't mount it towards the front of the vehicle then it can be mounted in any of the standard MAVLink orientations defined in [MAV_SENSOR_ORIENTATION](https://mavlink.io/en/messages/common.html#MAV_SENSOR_ORIENTATION).
The orientation follows the same frame convention as when [orienting the flight controller](../config/flight_controller_orientation.md#calculating-orientation).

If you're using the normal [Compass Calibration](../config/compass.md) process (with parameter [SENS_MAG_AUTOROT](../advanced_config/parameter_reference.md#SENS_MAG_AUTOROT) enabled), the orientation should be detected automatically.
Otherwise you can directly select the appropriate value in [CAL_MAGn_ROT](../advanced_config/parameter_reference.md#CAL_MAG1_ROT) for up to three compasses.

:::warning
You must mount the compass in a supported orientation!

If you mount the compass at an orientation that isn't supported, for example `Yaw 30`, PX4 will detect the closest supported value.
This will result in errors/warnings, even if the calibration appeared to succeed.
:::

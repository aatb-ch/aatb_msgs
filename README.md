# aatb_msgs

ROS2 package for custom messages, services and actions for [AATB](https://aatb.ch/) works.

## Messages

### Track.msg
Represents a single tracked object.

Fields:
- `uint32 id` - Unique identifier for the track
- `builtin_interfaces/Time entered` - Timestamp when the track was first detected
- `builtin_interfaces/Duration since` - Duration since the track was created
- `bool moving` - Whether the track is currently moving
- `geometry_msgs/Pose pose` - Current pose of the tracked object

### Tracks.msg
Container for multiple Track messages.

Fields:
- `std_msgs/Header header` - Standard ROS header with timestamp and frame
- `Track[] tracks` - Array of Track messages

## Building

```bash
colcon build --packages-select aatb_msgs
```

## Usage

After building, source the workspace and use the messages in your ROS2 nodes:

```python
from aatb_msgs.msg import Track, Tracks
```

## License

MIT - See LICENSE file for details
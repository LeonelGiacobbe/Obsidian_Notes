We can record agent behaviors and results, similar to how `bags` in [[ROS2]] work.

# Wrappers

## `RecordEpisodeStatistics`

> Records total rewards, episode length, and time taken
- Called with `env = RecordEpisodeStatistics(env, buffer_length= )`

## `RecordVideo`
> Renders mp4 videos of the agents and their environments

- Called with `env = RecordVideo(env, video_folder= , name_prefix= , episode_trigger= )`



# Recording during training
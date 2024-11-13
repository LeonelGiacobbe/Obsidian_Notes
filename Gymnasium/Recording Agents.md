We can record agent behaviors and results, similar to how `bags` in [[ROS2]] work.

# Wrappers

### `RecordEpisodeStatistics`

> Records total rewards, episode length, and time taken
- Called with `env = RecordEpisodeStatistics(env, buffer_length= )`

### `RecordVideo`

> Renders mp4 videos of the agents and their environments

- Called with `env = RecordVideo(env, video_folder= , name_prefix= , episode_trigger= )`

> Check [[Creating an environment]] for more details on `env`

# Recording during training
- It's not practical to record every single episode during training, since there could be hundreds of thousands of them.
- The wait Gymnasium solves this is by only recording 1 of `x` episodes, while noting the statistics for every single episode.

### Code Example

```python
import logging

import gymnasium as gym
from gymnasium.wrappers import RecordEpisodeStatistics, RecordVideo

training_period = 250  # record the agent's episode every 250
num_training_episodes = 10_000  # total number of training episodes

env = gym.make("CartPole-v1", render_mode="rgb_array")  # replace with your environment
env = RecordVideo(env, video_folder="cartpole-agent", name_prefix="training",
                  episode_trigger=lambda x: x % training_period == 0)
env = RecordEpisodeStatistics(env)

for episode_num in range(num_training_episodes):
    obs, info = env.reset()

    episode_over = False
    while not episode_over:
        action = env.action_space.sample()  # replace with actual agent
        obs, reward, terminated, truncated, info = env.step(action)

        episode_over = terminated or truncated

    logging.info(f"episode-{episode_num}", info["episode"])
env.close()
```

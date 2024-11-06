>[!warning] 
>Environments should always inherit from gymnasium.Env

In Gymnasium, there's  parts to a "game":
- [[Observations]]: provides the location of our agent(s) and target(s)
warn

### Setup
1) Define observation and action [[Spaces]]
	- The action space is the set of possible inputs
	- The observation space is the set of possible outputs


```python
from typing import Optional
import gymnasium as gym
import numpy as np


class myEnv(self):

	def __init__(self):
		self.observation_space = gym.spaces.Dict(
            {
                "agent": gym.spaces.shape("params"),
                "target": gym.spaces.shape("params"),
            }
        )
        
		self.spaces.Discrete(num) # num is the amount of
								  # possible movements
	  self._action_to_direction = {
			# Dict to map num of actions in space to directions in world
		}
		
	def _get_obs(self): # Returns current state before resetting or stepping
        return {"agent": self._agent_location, "target": self._target_location}
        
    def _get_info(self):
        return {
            "distance": np.linalg.norm(
                self._agent_location - self._target_location, ord=1
            )
        }
```


### Reset 
Used to reset the world and run a new instance. 
Takes two parameters:
	- `seed`: randomizes the world
	- `options`: sets constraints on the environment

```python

def reset(self, seed: Optional[int] = None, options: Optional[dict] = None):
        # We need the following line to seed self.np_random
        super().reset(seed=seed)

        # Choose the agent's location uniformly at random
        self._agent_location = self.np_random.integers(0, self.size, size=2, dtype=int)

        # We will sample the target's location randomly until it does not coincide with the agent's location
        self._target_location = self._agent_location
        while np.array_equal(self._target_location, self._agent_location):
            self._target_location = self.np_random.integers(
                0, self.size, size=2, dtype=int
            )

        observation = self._get_obs()
        info = self._get_info()

        return observation, info
```

We can use options to, for example, not randomize the state of the agent and have it always start at the same pose / rotation.


### Step
- Takes an action as a parameter and calculates the state of the environment after executing that action.
- Returns the tuple `(next obs, reward, terminated?, truncated?, aux info)`
- Usually want to map the discrete actions declared in the constructor to cartesian or angular movement on our nD grid.
	- For example `action(left) = [-1.0,0.0,0.0]` move 1 in the negative x direction
- Computes reward by comparing current state to goal state

```python
def step(self, action):
        # Map the action (element of {0,1,2,3}) to the direction we walk in
        direction = self._action_to_direction[action]
        # We use `np.clip` to make sure we don't leave the grid bounds
        self._agent_location = np.clip(
            self._agent_location + direction, 0, self.size - 1
        )

        # An environment is completed if and only if the agent has reached the target
        terminated = np.array_equal(self._agent_location, self._target_location)
        truncated = False
        reward = 1 if terminated else 0  # the agent is only reached at the end of the episode
        observation = self._get_obs()
        info = self._get_info()

        return observation, reward, terminated, truncated, info
```


### Registering and making the environment
Commonly done with `gymnasium.make("aaa/bbb/ccc)`
In Gymnasium, environment IDs are created by the following format:
- `namespace/env_name/version`
	- `namespace` and `version` are optional, but recommended
```python
gym.register(
    id="gymnasium_env/GridWorld-v0",
    entry_point=GridWorldEnv,
)
```

We can check if the environment was successfully registered using `gymnasium.pprint_registry()`
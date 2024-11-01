
```python 
import fastf1
# Loading qualifying from 7th race in 2021
session = fastf1.get_session(2021, 7, 'Q')
# '7' can be replaced with the string name of the grand prix. Does not have to match the exact official name.
session.name
# 'Qualifying'
session.date
# Timestamp('2021-06-19 13:00:00')
```


### The `Event` class 
- Contains more detailed information about the event
	- round number
	- Country
	- location
	- etc 
- Called with `session.event`
	- access individual elements -> `session.event['field]`
- Or directly with `event = fastf1.get_event(year, number)`
- Subclass of `pandas.series`


### `EventSchedule`  class 
- Loads all `events` in a season
- Subclass of `pandas.DataFrame`
- Can select specific events with `get_event_by_round` or `get_event_by_name`
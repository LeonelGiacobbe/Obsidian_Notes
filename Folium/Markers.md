>[!tip] Used to highlight data in maps

Syntax:
```python
folium.Marker(
    location=[N/S, E/W],
    tooltip="Click me!",
    popup="some data",
    icon=folium.Icon(icon="cloud"),
).add_to(mapName)
```
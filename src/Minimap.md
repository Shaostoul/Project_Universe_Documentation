# Minimap
- Minimaps are saved localy
- Minimaps has a sync option to share it to a team with conditions (Teammate has antenna and is in range, antenna signal is not disturbed, etc.)
- Minimaps can be uploaded to "faction server" which means all faction member has access to it
- Minimaps can be created for ships, facilitys and stations (Grids)
- Rooms can be labled by the Player
- Rooms are mapped on enter
- Doors are mapped on use
- Minimaps have minimized version and a full screen Version

## Technical Concept
- Per Grids 1 Minimap File saved on Disk / Database
  - Each Layer / Floor is a own Chapter
  - Each Room can have multiple comments by 1 author
  - Each Room can have multiple names by 1 author
  - Each Rooms comment and names can be toggled between from the UI
- Minimaps can be cooperated on, the one that places down the map is the host
- Server is the relay for the connections
- Read and Write rights are defined by the one player that placed down the map

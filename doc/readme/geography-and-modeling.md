# Geography and 3D modeling

Open a practice project in Story Workspace. You can start with the 2D map to plan a location, build a measured model in chat, and inspect the result in the same place and time as your scenes.

## Establish a coordinate frame

1. Choose a landmark for the origin. Give your assistant the scale in metres, the direction of story north, and the reference height for zero elevation. X and Y locate a point on the map. Z measures height above or below your reference.
2. Open **Elevation** to inspect the saved terrain. Tap a covered point in the 2D map and read the two ground profiles through it. A gap means that no ground elevation has been recorded there.
3. To use an overhead image as a measured overlay, select its exact version, match identifiable points to surveyed or authored ground coordinates, and check the fit with a separate point. You can also keep an unregistered image as a visual reference.

## Build and export a model

1. Ask **“Preview a four-by-three-metre rectangular solid, 2.5 metres high. Show me the horizontal section halfway up and the solid volume.”** Check for a 12 m² section and 30 m³ volume. The preview lets you change the measurements before saving.
2. Ask to save the reviewed model and place it at coordinates you specify. Name the parent if the model belongs inside another place. An asset describes the geometry. Each instance has its own position, rotation, and scale.
3. To build up a structure, try **“Preview six repeated floor slabs around an open courtyard. Show me the section through one floor.”** Profiles can have holes, and a loft can connect cross-sections of different sizes. You can also ask for a Boolean cut, the clearance between surfaces, or the distance between two anchors. Tell the assistant which measurement you need.
4. For a change during the story, name the event and the object. Ask to preview the new position, check which children move with it, and then save the change. Reopen Geography at an earlier anchored scene to inspect the earlier placement.
5. Choose **Map controls → Data → Download GLB** to save the selected models when your chat host supports file saving. In chat, you can also ask for a saved export as GLB or zipped glTF. Specify the selection, layer, and event if you need to reproduce a particular scene. Terrain is viewed separately and is outside the model export.

## Explore the map

Open **Geography** for the whole project, or use **Open in Geography** on a Location record. **Fit map** shows the full terrain frame. **Fit selection** brings a selected room, building, or object into view. A location with no saved position stays unplaced.

In **2D map**, open **Planning shapes** and draw a point, line, rectangle, or polygon. **Preview shape** shows the applicable measurements, such as length, perimeter, or area. Select **Save shape** when the layout is right. Drape a shape over terrain to follow local grade, or supply its elevations to control the height yourself.

Choose **3D view** to orbit the terrain and models. Drag to orbit, use two fingers to pan and zoom, and tap a model to inspect it. Use **Map controls → Layers** to show buildings, terrain, water, districts, or planning shapes. **Inspect underneath** lets you examine a basement or tunnel. The Physical, Augmented, and Historical reality layers show the geometry authored for each.

For the tools behind these steps, see the [tool reference](../storyroom-tools.md).

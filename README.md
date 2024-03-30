# Davinci Resolve - Video Editing Tool
## Fusion Path
### Travel Path
1. Import an immage to the video track 1
2. Go to 'Fusion', select 'MediaIn1' and press shift+space to add 'Paint' tool
3. Select 'Paint1' and change to 'PolyLineStroke' -> drow the map path
4. Change the color, size, softness, Spacing (in Stroke Controle)
5. Set a key frame in first frame in 'write on' of the 'Stroke Controle' section
6. Set a end key frame and change 'write on' END to 1.0
7. Copy 'Paint1' and paste
8. Select 'Paint1_1' and go to 'Modifiers'
9. Go to first frame and set 'write on' Start and End to 0.001


## Fusion Particles
### Logo dissolve
1. Go to 'Effects', search for 'Fusion Composition' to timeline
2. Select the clip and change the duration (cmd + D) to 7 seconds
3. Go to 'Fusion' section, grab 'pEmitter' and 'pRender' nodes to the fusion plane
4. Connect 'pEmitter' -> 'pRender' -> 'MediaOut1'
5. Select 'pEmitter' and change the number of particles 70000
6. Select 'pRender' make sure the output mode '2D'
7. Select 'pEmitter' again and select 'Region' as 'Bitmap' in 'Region' section
8. Drag the logo as a node (MediaIn1) and connect to 'pEmitter'.
9. Select 'pEmitter' -> controlers 'Color' -> change to 'use color from region' from 'use style color'
10. Disconnect the logo (MediaIn1) and drag and drop to left viewer to see the resolution
11. Select MediaIn1 and Shift+space to add 'Resize' fn
12. Select 'Resize1' -> click 'Reset Size' in the 'inspector'
13. Drag and drop 'Resize1' to left viewer to see the size
14. Select 'Resize1' -> Shift+space to add 'Transform' fn
15. Drag and drop 'Transform1' to left viewer and chaneg the size, aspect, possition from the 'inspector'
16. Drag 'Plogon' mask to the fusion plane
17. Drow a pligon partially cover the logo and big enough to cover the full logo later
18. Copy the mask (cmd+c) and paste using cmd+shift+v to create new instace of the mask (Instance_Polygon1)
19. Select 'Instance_Polygon1' and in the 'inspector', right click on 'boarder width' -> select 'Deinstance' : to change the border width without changing the original mask.
20. Uncheck the 'Solid' option of the 'Instance_Polygon1'
21. Drag and drop a 'Merge' node to the fusion plane
22. Connect output of 'Poligon1' mask's output to input of 'Merge1'
23. Connect output of 'Instance_Polygon1' to green arrow of the 'Merge1' (foreground)
24. Click on 'Merge1' -> change the 'Operator' from 'over' to 'xOR'
25. Select 'Instance_Polygon1' and change the 'Border Width' as needed : everything in the border is visible and black part invisible
26. Transfor the mask to black and white image by adding 'Bitmap' to the fusion plane: press shift+space
27. Connect 'Merge1' to 'Bitmap1'
28. Press shift+space again to add 'Matte Controle'
29. Connect 'Bitmap1' gray output to garbage input (gray arrow in the bottom) of the 'MatteControl1'
30. Connect 'Transform1' to yellow arrow of the 'MatteControl1'
31. Connect 'MatteControl1' to 'pEmitter'
32. Drag 'MediaOut1' to right plane to see the status
33. Select 'MatteControl1' -> select 'Garbage Matte' to 'Invert' in the 'Inspector'
34. Select 'pEmitter' -> shift+space and search for 'pDirectionalForce' and add
35. Select 'pDirectionalForce1' and change the direction to 45
36. Select 'pDirectionalForce1' and shift+space for search 'pTurbulence' and add
37. Change the properties x,y,z 'Strength' to .2, .2, .3 and change the 'Density' to 50
38. Select 'Plogon1' -> move to frame 0 -> add a key frame in 'center'
39. Drag the mask out of the logo and Pull over to cover the full logo
40. Multi select 'MediaIn1' + 'Resize1' + 'Transform1' and paste to the fusion plane
41. Connect the segment through a Merge (select output of 'Transform1_1' drag and drop to output of 'pRender') : Make sure 'Transform1_1' and 'Merge2' connect via Grean connect
42. Drag 'Merge2' to right plane to see the status
43. Copy 'Plogon1' mask and paste to the fusion plane and connect to 'Merge2' node
44. Select 'Plogon1_1' and tick on 'Invert' and 'solid'
45. Change the Soft Edge too
46. Render the animation
<img width="722" height="400" alt="Logo dissolve" src="https://github.com/jayasankai/DavinciResolve/assets/61721893/ea4d7b09-54c6-4b67-ac22-b39732617667">
 

## Video Transition
### Ink effect
1. Import 'Ink Drop Reveal - 3.mp4' to video track 2
2. Invert color : Select 'Color' section, search for 'Invert Color' from 'Effects'
3. Drag and drop the effect to video
4. Add background : Go to 'Edit section, Select 'Paper' from 'Generators' and add to video track 1
5. Change the paper properties in paper in 'Inspector' section to make it 'Old Matt' paper
6. Select 'Ink Drop' video track and go to 'Inspector' -> select 'Lum' from the 'composite' mode
7. Import the video for Ink Transition. use video track 3
8. Select the added video and go to 'Inspector' -> select 'Foreground' from the 'composite' mode
<img width="722" height="400" alt="Ink effect" src="https://github.com/jayasankai/DavinciResolve/assets/61721893/b8833bc4-827a-4467-ac2e-9af6c46702dd">


## Text Title Effects
### TEXT BEHIND moving objects
#### Method 01: By manually selecting the object
1. Import a video file to viode track 1
3. Add a text title (or text+) "TEXT" to viode track 2
4. Duplicate the video file in video track 1 to track 3
5. Select duplicetd video, Add 'Alpha output' channel to video
6. Go to 'Color' section, Select 'Windlow' tool, Select 'Pen' tool
7. Select the front moving object to track
8. Go to 'Tracker' section, select 'Frame', then play 'Track Fwd and Revs' to track the selection. Make sure 'Cloud Tracker' enabled.
<img width="722" height="400" alt="TEXT BEHIND moving objects: By manually selecting the object" src="https://github.com/jayasankai/DavinciResolve/assets/61721893/7837bdc0-74f5-41fa-a455-71b80a4c64bf">

#### Method 02: Using 3D qualifier
1. Import a video file to viode track 1
3. Add a text title (or text+) "TEXT" to viode track 2
4. Duplicate the video file in video track 1 to track 3
5. Select duplicetd video, Add 'Alpha output' channel to video
6. Go to 'Color' section, Select 'Windlow' tool, Select 'Qualifier' tool, Switch to '3D' qualifier.
7. Select the front moving object to track, Use +ve, -ve pens to refine the selection
<img width="722" height="400" alt="TEXT BEHIND moving objects: Using 3D qualifier" src="https://github.com/jayasankai/DavinciResolve/assets/61721893/68f90212-98e8-4d34-9587-7fc2da19478e">

### BEST Text EFFECTS in Davinci Resolve
#### Text Effect 01: Video within TEXT
1. Import a video file to viode track 2
2. Add a text title (or text+) "TEXT" to viode track 1
3. Deactivate the video track to visualize the title track to edit
4. Edit as you need : Hint : use large font with bold text
5. Activate the video track and go to "Inspector" -> change 'Composite Mode' to 'Foreground'
6. Select 'text' track and go to "Inspector" -> 'Settings menu' menu -> change 'Composite Mode' to 'Alpha'
<img width="722" height="400" alt="Video within TEXT" src="https://github.com/jayasankai/DavinciResolve/assets/61721893/7b188239-da4b-40eb-aa92-6a2afe4dfd33">

#### Text Effect 02: Text with glitch effect
1. Add a title 'Text' to the track 01
2. Right click on text tract -> create 'New compound clip'
3. Go to 'Affects' -> select 'Degital Glitch' -> Grag and drop to compound text

#### Text Effect 03: Type write text effect
1. Import a video file to viode track 1
2. Add a text+ "TEXT" to viode track 2, change the font to 'type writter' font and change the font size
3. Place the starting key to first frame of the text -> go to "Inspector" -> 'Title menu' menu -> change 'write on''s end value to 0.0
4. Place the end key frame of the text -> go to "Inspector" -> 'Title menu' menu -> change 'write on''s end value to 1.0

#### Text Effect 04: Neon text
1. Go to 'Fusion' section, add a 'Text+' node
2. Activate the title by clicking 'activation' dot in the 'text+' node
3. Open the 'Inspector' menu, Type the text, Change the font..etc
4. Change the color to 'BLACK'
5. Duplicate the text by copy paste
6. Change the color to 'NEON BLUE' on second text
7. Select the second text and press 'shift+space' to get affect menu
8. Select the 'Glow' affect and 'Add'
9. Select the glow 1 node and press 'shift+space' to get affect menu
8. Select the 'Glow' affect again and 'Add' 2nd glow
9. Select the glow 2 and increase the glow size to 50%
10. Select the glow 2 node and press 'shift+space' to get affect menu
11. Select the 'Glow' affect again and 'Add' 3rd glow
12. Select the glow 3 and increase the glow size to 100%
13. Select the first frame of the video, then select 'Merge 2' node, go to the 'Settings' menu, Create a key frame in the 'Blend' option
14. Add a key frame of blend 0
15. Move few frames and change the blend to 1, this will add new key frame with NEON light
16. Move few frames and change the blend to 0, this will add new key frame with NO-NEON light
17. Repeate this as you need until Neon to off
<img width="722" height="400" alt="Without NEON" src="https://github.com/jayasankai/DavinciResolve/assets/61721893/7334b3b0-4735-4c31-b19f-bdb5cbdceaa1">
<img width="722" height="400" alt="With NEON" src="https://github.com/jayasankai/DavinciResolve/assets/61721893/176c68db-09aa-4871-bd29-468039823164">

#### Text Effect 05: Cinamatics text
1. Go to 'Fusion' section, add a 'Text+' node
2. Makesure the frame is in first key
3. Open the 'Inspector' menu, Type the text, Change the font..etc
4. Right click on the body of text update section, select 'Follower'
5. Then open the 'Modifiers' tab, Change the 'Automatic' order to 'Random but one by one' and increase the 'delay' to 2.0
6. Open the menu 'shading', open the 'softness' section of the tab, set two key frams to x and y (click on the key frame diomand), increase the value to max (20.0)
7. Move the frame to end the animation and change the x and y values to minimum in softness section. This will automatically add key to the frame.
<img width="722" height="400" alt="Cinamatics text" src="https://github.com/jayasankai/DavinciResolve/assets/61721893/a68c1dab-7a14-4187-a70b-353f4f6cde08">

#### Text Effect 06: Hand writting text
1. Import a video file to viode track 1
2. Go to 'Fusion' section, select 'MediaIn1' node, add a 'Text+' node
3. Select the Text+ node, go to 'Inspector', Type the text, Change the font..etc
4. In the layout tab, modify change the x and y axis to place the title
5. Select text1 node,
6. Go to 'Effects', search for 'Mask Paint'
7. Double click to add, this will create a new 'MaskPaint1' node and attach to the 'Text1' node
8. Select 'MaskPaint1' node and select 'Stroke' brush in the main window
9. Text will dissapear
10. Go to 'Mask' tab in the 'Inspector', activate 'Invert' to see the text
11. Go to 'Controles' tab in the 'Inspector', open 'Brush Controles', modify the size (increase) and the softness (decrease) of the brush
12. Open 'Stroke Controles', change the 'Stroke Animation' to 'write on'
13. Prepare for animation : Set the screan window to show all the letters
14. Without releasing the mouse, erase the lettters as we write letters, this will add many key frames with the movements
15. Go to 'Mask' tab in the 'Inspector', de-activate 'Invert' to see the stroke
16. Play and see : only partial of the letters appear :: need to adjest the duration of the writting
17. Activate the 'Keyframes' tab (near to the 'Inspector')
18. Select all the frames (appeas in yellow), right click on it and select 'Time streching'
19. Play and adjest accordingly
<img width="722" height="400" alt="Hand writting text" src="https://github.com/jayasankai/DavinciResolve/assets/61721893/cc968fea-8f09-4123-91c0-e1f0659ca7ea">

#### Text Effect 07: Mirror text
1. Go to 'Fusion' section, add a 'Text+' node
2. Open the 'Inspector' menu, Type the text, Change the font..etc
3. Select 'Text1' node, copy to duplicate and paste using menu
4. Create a merge node by linking endpoint of the duplicate text to the 'Merge1' endpoint
5. Select 'Merge2' node, open the 'Inspector' menu, click on the 'flip horizontal' icon to flip the text
6. Go to the 'Settings' in the 'Inspector' menu, reduce the size of 'Blend' to 50%
7. To modify the reflection letters, Click on 'Text1_1' and open the 'transform' tab in the 'Inspector', open 'Shear' and change as you need.
8. Select 'Text1_1' node, add 'Rectangle' shaped mask
9. Move down the mask to cut the latter part of the text.
10. Increase the 'Soft edge' to apear letters
<img width="722" height="400" alt="Mirror text" src="https://github.com/jayasankai/DavinciResolve/assets/61721893/cfe373d7-6cc9-4962-a30d-d9469ce1aa19">

#### Text Effect 08: Camera Fly-Through 3D Text
1. Go to 'Effects', search for 'Fusion Composition' to timeline
2. Select the clip and change the duration as needed (cmd + D)
3. Go to 'Fusion' section, grab 'Renderer 3D' and 'Merge 3D' nodes to the fusion plane
4. Link output of each node to input in the sequence of 'Merge3D1' -> 'Renderer3D1' -> 'MediaOut1'
5. Drag and drop the 'footage' (MediaIn1) and 'Image Plane 3D' nodes to the fusion plane
6. Link each node in the sequence of 'MediaIn1' -> 'ImagePlane3D1' -> 'Merge3D1'
7. Drag and drop 'Merge3D1' to left viewer plane
8. If you see black bars in the view, click on the 'MediaIn1' then Shift+space to open effects.
9. Search for 'Transform (Xf)' node and add
10. Select 'Transform1' node, change the 'size' attribute to fit the video to plane
11. Drag and drop the 'Camera 3D' and 'Text 3D' nodes to the fusion plane. Join each to 'Merge3D1'.
12. Select the 'Camera3D1' change the z-axis to view the text and plane.
13. Select the 'Text3D1', add the text in 'Inspector'. If the text not visible correctly, change the z-axis also in 'Transform' tab in the 'Inspector'.
14. Add the 'Extrusion Depth' to text in 'Extrusion' section in the in the 'Inspector'.
15. Add Texture: Select 'Text3D1', press Shift+space to add 'Replace Matetial 3D'
16. Go to 'Effects' -> 'Templates' -> 'Fusion' -> 'Shaders' -> select 'Chrome'. Drag and drop to the fusion plane. Link it to the 'ReplaceMatetial3D1'
17. Select the first key frame and pin
18. Move to end frame of the animation and change the x,y,z axis to make a fly-through
19. Go to 'Edit' Segment and check how it looks like.
<img width="722" height="400" alt="Camera Fly-Through 3D Text" src="https://github.com/jayasankai/DavinciResolve/assets/61721893/6b21a662-7538-4a6c-a2b9-ea56de792f63">




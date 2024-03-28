# Davinci Resolve - Video Editing Tool
## Text Title Effects
### 7 BEST Text EFFECTS in Davinci Resolve 18
#### Text Effect 01: Video within TEXT
1. Import a video file to viode track 2
2. Add a text title (or text+) "TEXT" to viode track 1
3. Deactivate the video track to visualize the title track to edit
4. Edit as you need : Hint : use large font with bold text
5. Activate the video track and go to "Inspector" -> change 'Composite Mode' to 'Foreground'
6. Select 'text' track and go to "Inspector" -> 'Settings menu' menu -> change 'Composite Mode' to 'Alpha'
<img width="722" height="400" alt="image" src="https://github.com/jayasankai/DavinciResolve/assets/61721893/7b188239-da4b-40eb-aa92-6a2afe4dfd33">

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
<img width="722" height="400" alt="Without NEON" src="https://github.com/jayasankai/DavinciResolve/assets/61721893/a68c1dab-7a14-4187-a70b-353f4f6cde08">

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
<img width="722" height="400" alt="image" src="https://github.com/jayasankai/DavinciResolve/assets/61721893/cc968fea-8f09-4123-91c0-e1f0659ca7ea">






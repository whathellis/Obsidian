---
date: 2024-08-02
topics:
  - "[[Blender tutorial|Blender tutorial]]"
  - "[[Lip sync|Lip sync]]"
q-type: article
---

#### [[../../07/YouTube/Watched/Tutorial/Easy Lip Syncing, Automated Puppet-style|Easy Lip Syncing, Automated Puppet-style]]
1. Model a puppet head
	Make shape key for the open mouth
2. Add an empty
	1. add Z axes keyframe
3. In the channel menu select **sound to samples** and chose the audio
4. Go to **Video Sequence** and click *Add* and *Sound* 
5. Check *Audio Scrubbing* in **Timeline** *Playback* and chose *Frame Dropping* for Sync
6. Add Driver to the mouth shape key and select the empty
	1. Use just $var$
#### [[../../07/YouTube/Watched/Tutorial/Easy Mouth Rig in Blender|Easy Mouth Rig in Blender]]
1. make bones 
	- for the head
		- jaw
		- upper lip
		- bottom lip
		Change the rotation point to **Active Element** by clicking `.` 
2. Select the head + `Shift` select the rig - **parent with empty groups**
	- Parent tees
3. Go to pose mode
	1. Ander the edit turn off **Lock Object Modes**
	2. Select the head from the outliner
	3. Go to weight paint
4. Weight paint
	- Options
		- Check **Auto Normalise**
5. Bottom lip ^6f57e1
	- Go to bone constrains
	- Add **Copy Location**
		- Select jaw bone
	- Add **Copy Rotation**
		- Select jaw bone
		- Change the *Target* and the *Owner* to local
		- Set *Mix* to after original
6. Jaw
	- Add **Limit Rotation**
	- Set  the *Owner* to local
	- Limit *X*:
		- Min: 0°
		- Max: 30°
		Check *Effect Transform*
7. Top lip 
	- Repeat [[Mouth Animation#^6f57e1|this]] for chewing
	- Make the same [[Mouth Animation#^2ad01c|thing]] but for the *Influence*
1. Add **Shape Keys** for smiling ^2ad01c
	- change the *Range Min* to -1 for frowning
	- add a new bone
		- turn off *Deform* in the bone settings
		- add **Limit Location**
		- Set  the *Owner* to local
		- check all the axis
			- Limit the ***First key*** axis to 0.2 ^3da2d3
			- Repeat [[Mouth Animation#^3da2d3|this]] for other keys
	- For the first key Right click the *value* and add **Driver** ^2a3618
		- Select the bone
		- Changing location
		- Target: chose ***the axis***
		- Space: Local space
		- Edit the expression to $var*5$ (so the result was [[Mouth Animation#^3da2d3|0.2]]*5=1)
	- Repeat [[Mouth Animation#^2a3618|this]] for other keys

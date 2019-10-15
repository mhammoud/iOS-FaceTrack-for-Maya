# iOS FaceTrack for Maya

iOS FaceTrack for Maya allows you to use your iPhone X/XS/XS Max for facial motion capture for character animation in Autodesk's Maya.

## How does it work? ##

<img align="right" src="giphy.gif">

The iPhone X introduced new camera technology to allow facial recognition for FaceID. The "TrueDepth" camera uses advanced technology to map the geometry of your face by projecting and analyzing over 30,000 invisible dots to create a depth map of your face. Apple uses this geometry analysis for their Memoji stickers, which are able to be animated to your facial expression in real time. Apple's ARKit (Augmented Reality Library) provides an API which allows you to retrieve "blend shapes", which is a dictionary of coefficients for detected facial expressions. For example, leftEyeTwitch is a blend shape that describes the amount of twitching that is occurring in an eye, with 0 having no twitch, and 1 being that the eye has completely blinked. 

You can read about ARFace and blendshapes at Apple's ARKit documentation [here](https://developer.apple.com/documentation/arkit/arfaceanchor/2928251-blendshapes).

iOS FaceTrack for Maya is able to query the blend shapes that are geometrically mapped from the camera, and then transmit the dictionary of coefficients for each blend shape over WiFi to a computer that has Autodesk's Maya application suite. A python script will then be able to programmatically update the attributes of a 3D facial model (after rigging) to produce values at a particular keyframe. As a result, this creates an animation in Maya of the animation that was produced by the actor in front of the iPhone camera. 

This is a **work in progress**. At the moment, I am able to use ARKit for facial recognition to detect facial expression and compute the amount of movement of facial features by querying blend shapes. I can transfer the attributes over the iPhone using a USB and use a Python script to update the attributes of a 3D Model. The next steps are to implement a socket controller to transfer the blend shapes dictionary over WiFi (a opposed to USB), and to create a Python script that will produce a full .anim file of the blend shapes values at each keyframe for the 3D model.





# WebAR chair

AR assignment. A chair you can place in your room from the browser, no app install needed.

Live: https://marinprusac.github.io/webar-tutorial/

The start page (`index.html`) has two buttons, one for each tracking method.

## Surface-based part

- Page: `surface.html`
- Uses Google's [model-viewer](https://modelviewer.dev/)
- When you tap the AR button, the phone opens its own AR viewer (Quick Look on iPhone, Scene Viewer on Android). That viewer finds the floor and you can place, move and rotate the chair.
- `chair.glb` is used on Android, `chair.usdz` on iPhone

## Marker-based part

- Page: `marker.html`
- Uses [MindAR](https://github.com/hiukim/mind-ar-js) image tracking with [A-Frame](https://aframe.io/)
- Marker is the Lund University seal (`lund.png`). Print it or open it on another screen, point the camera at it and the chair shows up standing on it and spins
- When the marker is found the text at the top changes to "Found it!", and goes back when it's lost
- `lund.mind` is the compiled tracking data for `lund.png`, made with the MindAR image compiler

## Where stuff comes from

- Forked from [gunterAlce/webar-tutorial](https://github.com/gunterAlce/webar-tutorial) (their index.html is now my surface.html, plus style.css)
- Marker page is based on the MindAR image tracking example
- Lund University logo from [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Logotyp_Lunds_universitet_(vit).png).
  I cropped out the seal without the text, made it dark blue and made the lines thicker, because the thin gold lines didn't get recognized
- Chair model is SheenChair from [Khronos glTF Sample Assets](https://github.com/KhronosGroup/glTF-Sample-Assets) (CC0)

## What I changed

- Replaced the sample models with the chair
- Made the USDZ version for iPhone in Blender (import glb, export usdz)
- Pointed `src` and `ios-src` to my repo
- The loading text never went away in the original, so it now hides when the model loads
- Added a short hint under the model
- Made a start page with links to both parts
- Removed the old sample models

For the marker page I wrote `marker.html` using the example as a starting point: swapped their model for the chair, rotated and scaled it so it stands on the marker, added the spinning and the found/lost text. Swapped their example marker for the Lund University seal.

I used WebAR instead of the Unity workshops because I only have an iPhone and no Mac, so I can't build the Unity apps for my phone.

## How to test

- Surface: open the live link on a phone, pick Surface, tap the AR button and point it at the floor
- Marker: open the live link, pick Marker, allow the camera and point it at `lund.png`

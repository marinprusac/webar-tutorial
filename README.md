# WebAR chair

AR assignment. A chair you can place in your room from the browser, no app install needed.

Live: https://marinprusac.github.io/webar-tutorial/

## Surface-based part

- Page: `index.html`
- Uses Google's [model-viewer](https://modelviewer.dev/)
- When you tap the AR button, the phone opens its own AR viewer (Quick Look on iPhone, Scene Viewer on Android). That viewer finds the floor and you can place, move and rotate the chair.
- `chair.glb` is used on Android, `chair.usdz` on iPhone

## Marker-based part

- Page: `marker.html` (also linked from the main page)
- Uses [MindAR](https://github.com/hiukim/mind-ar-js) image tracking with [A-Frame](https://aframe.io/)
- Point the camera at `card.png` (print it or open it on another screen) and the chair shows up standing on it and spins
- When the marker is found the text at the top changes to "Found it!", and goes back when it's lost
- `card.mind` is the compiled tracking data for `card.png`

## Where stuff comes from

- Forked from [gunterAlce/webar-tutorial](https://github.com/gunterAlce/webar-tutorial) (index.html and style.css)
- Marker page is based on the MindAR image tracking example, `card.png` and `card.mind` are from their examples
- Chair model is SheenChair from [Khronos glTF Sample Assets](https://github.com/KhronosGroup/glTF-Sample-Assets) (CC0)

## What I changed

- Replaced the sample models with the chair
- Made the USDZ version for iPhone in Blender (import glb, export usdz)
- Pointed `src` and `ios-src` to my repo
- The loading text never went away in the original, so it now hides when the model loads
- Added a short hint under the model
- Removed the old sample models

For the marker page I wrote `marker.html` using the example as a starting point: swapped their model for the chair, rotated and scaled it so it stands on the card, added the spinning and the found/lost text. Also removed a rotation tag from `card.png` because it showed up sideways in some viewers.

I used WebAR instead of the Unity workshops because I only have an iPhone and no Mac, so I can't build the Unity apps for my phone.

## How to test

- Surface: open the live link on a phone, tap the AR button and point it at the floor
- Marker: open https://marinprusac.github.io/webar-tutorial/marker.html, allow the camera and point it at `card.png`

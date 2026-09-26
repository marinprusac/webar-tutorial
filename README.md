# WebAR chair

AR assignment. A chair you can place in your room from the browser, no app install needed.

Live: https://marinprusac.github.io/webar-tutorial/

## Surface-based part

- Page: `index.html`
- Uses Google's [model-viewer](https://modelviewer.dev/)
- When you tap the AR button, the phone opens its own AR viewer (Quick Look on iPhone, Scene Viewer on Android). That viewer finds the floor and you can place, move and rotate the chair.
- `chair.glb` is used on Android, `chair.usdz` on iPhone

## Where stuff comes from

- Forked from [gunterAlce/webar-tutorial](https://github.com/gunterAlce/webar-tutorial) (index.html and style.css)
- Chair model is SheenChair from [Khronos glTF Sample Assets](https://github.com/KhronosGroup/glTF-Sample-Assets) (CC0)

## What I changed

- Replaced the sample models with the chair
- Made the USDZ version for iPhone in Blender (import glb, export usdz)
- Pointed `src` and `ios-src` to my repo
- The loading text never went away in the original, so it now hides when the model loads
- Added a short hint under the model
- Removed the old sample models

## How to test

Open the live link on a phone, tap the AR button and point it at the floor.

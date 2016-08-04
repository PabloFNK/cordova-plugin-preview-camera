cordova-plugin-preview-camera
====================

This repository was copied with the idea to use it with <b>Meteor</b> with new features. The use for now is only with <b>Android</b><br/>
If you've got problems related with these new features or using it with Meteor add here an issue here but for further info would be better to publish them into main repository here:</br>
https://github.com/cordova-plugin-camera-preview/cordova-plugin-camera-preview/issues

Features added and tested so far:<br>
<ul>
<li>Auto zoom</li>
</ul>
All help would be really apreciated.<p>

<b>How to install with Meteor:</b><br>
Type in your terminal `meteor add cordova:cordova-plugin-preview-camera@0.0.11` (this version could change).<br>
Not tested in Meteor 1.4 yet.<br>

Npm: https://www.npmjs.com/package/cordova-plugin-preview-camera
<p>

------- Original info ---------<br>

Cordova plugin that allows camera interaction from HTML cod for showing camera preview below or above the HTML.<br/>

**May 18, 2016 - Plugin is starting to be maintained again, current development to get a decent stable updated version is happening on the fork [westonganger/cordova-plugin-preview-camera](https://github.com/westonganger/cordova-plugin-camera-preview/tree/skanygin). This will be merged into master here once its working. Please direct all pull requests over there until further notice.**

<p><b>Features:</b></p>
<ul>
  <li>Start a camera preview from HTML code.</li>
  <li>Drag the preview box.</li>
  <li>Set camera color effect.</li>
  <li>Send the preview box to back of the HTML content.</li>
  <li>Set a custom position for the camera preview box.</li>
  <li>Set a custom size for the preview box.</li>
  <li>Set a custom alpha for the preview box.</li>
  <li>Maintain HTML interactivity.</li>
</ul>

<p><b>Installation:</b></p>

```
cordova plugin add https://github.com/cordova-plugin-preview-camera/cordova-plugin-preview-camera.git
```

<b>Phonegap Build:</b><br/>

```
<gap:plugin name="cordova-plugin-preview-camera" />
```

<p><b>Methods:</b></p>


  <b>startCamera(rect, defaultCamera, tapEnabled, dragEnabled, toBack)</b><br/>
  <info>
  	Starts the camera preview instance.
  	<br/>
	<br/>
	When setting the toBack to TRUE, remember to add the style bellow on your app's HTML body element:
```
style="background-color='transparent'"
```
</info>

Javascript:

```
var tapEnabled = true; //enable tap take picture
var dragEnabled = true; //enable preview box drag across the screen
var toBack = true; //send preview box to the back of the webview
var rect = {x: 100, y: 100, width: 200, height:200};
cordova.plugins.camerapreview.startCamera(rect, "front", tapEnabled, dragEnabled, toBack)
```

<b>stopCamera()</b><br/>
<info>Stops the camera preview instance.</info><br/>

```
cordova.plugins.camerapreview.stopCamera();
```

<b>takePicture(size)</b><br/>
<info>Take the picture, the parameter size is optional</info><br/>

```
cordova.plugins.camerapreview.takePicture({maxWidth:640, maxHeight:640});
```


<b>setOnPictureTakenHandler(callback)</b><br/>
<info>Register a callback function that receives the original picture and the image captured from the preview box.</info><br/>

```
cordova.plugins.camerapreview.setOnPictureTakenHandler(function(result){
	document.getElementById('originalPicture').src = result[0];//originalPicturePath;
	document.getElementById('previewPicture').src = result[1];//previewPicturePath;
});
```


<b>switchCamera()</b><br/>
<info>Switch from the rear camera and front camera, if available.</info><br/>

```
cordova.plugins.camerapreview.switchCamera();
```

<b>show()</b><br/>
<info>Show the camera preview box.</info><br/>

```
cordova.plugins.camerapreview.show();
```

<b>hide()</b><br/>
<info>Hide the camera preview box.</info><br/>

```
cordova.plugins.camerapreview.hide();
```

<b>Base64 image:</b><br/>
Use the cordova-file in order to read the picture file and them get the base64.<br/>
Please, refer to this documentation: http://docs.phonegap.com/en/edge/cordova_file_file.md.html<br/>
Method <i>readAsDataURL</i>: Read file and return data as a base64-encoded data URL.

<b>Sample:</b><br/>
Please see the <a href="https://github.com/mbppower/CordovaCameraPreviewApp">CordovaCameraPreviewApp</a> for a complete working example for Android and iOS platforms.

<p><b>Android Screenshots:</b></p>
<p><img src="https://raw.githubusercontent.com/mbppower/CordovaCameraPreview/master/docs/img/android-1.png"/></p>
<p><img src="https://raw.githubusercontent.com/mbppower/CordovaCameraPreview/master/docs/img/android-2.png"/></p>

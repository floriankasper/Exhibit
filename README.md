# MDM Image Viewer
MDM Image Viewer is a managed screensaver App for tvOS intended to be used with Jamf Pro managed app configuration.

### Installation

A build of MDM Image Viewer is available for download from the [tvOS App Store](https://its.nebraska.edu). The current version should be deployed with App Configuration Preferences from Jamf Pro.



### Managed App Configuration Preferences
App configuration Preferences are currently required to load the CSV file location through the "edu.nebraska.ImageViewer.dataURL" preferences key. All available keys are shown here:

**edu.nebraska.ImageViewer.dataURL** (required)
URL of the CSV file containing image information. There is no default option for this key and the App will not function as built without this value loaded.
**edu.nebraska.ImageViewer.imageTimer** (optional)
Time (in seconds) of the image timer default. Image display time length is specified in the CSV file but will default to this option if nothing is entered in the file.
**edu.nebraska.ImageViewer.airplayViewTimer** (optional)
Time (in seconds) between movements of the AirPlay box. The default time is set to 33 seconds.
**edu.nebraska.ImageViewer.dataCheckTimer** (optional)
Time (in seconds) between checks for updates in the CSV file. The default time is set to 180 seconds.


*Sample configuration preferences:*
```xml
<dict>
	<key>edu.nebraska.ImageViewer.dataURL</key>
	<string>https://link.to.preferences.csv</string>
	<key>edu.nebraska.ImageViewer.imageTimer</key>
	<integer>10</integer>
	<key>edu.nebraska.ImageViewer.airplayViewTimer</key>
	<integer>25</integer>
	<key>edu.nebraska.ImageViewer.dataCheckTimer</key>
	<integer>600</integer>
</dict>
```

### CSV Image Playlist Settings Example
The CSV file liked in the managed preferences should show values including a header and in the order listed below. The "UpdateInterval" and "Cache" values are not currently used but should still be included within the CSV file.
Name | URL | Duration | UpdateInterval | StartOn | EndBy | Cache
:--- | :--- | :--- | :--- | :--- | :--- | :---
Test Image | https://example.com/image.png | 0:00:10 | 1:00:00 | 1/1/18 0:00 | 12/31/99 23:59 | yes

**Name** - Name of the image. This value is strictly for reference.
**URL** - Web location of the image file.
**Duration** - Length of time to display the particular image in **H:MM:SS** format.
**UpdateInterval** - *Currently Unused*
**StartOn** - Date and time to begin showing the specified image in the playlist in **M/d/yy H:mm** format.
**EndBy** - Date and time to stop showing the specified image in the playlist in **M/d/yy H:mm** format.
**Cache** - *Currently Unused*

## Errors and bugs

If something is not behaving intuitively, it is a bug and should be reported.
Report it here by creating an issue: https://github.com/qharouff/mdm-image-viewer/issues

Help us fix the problem as quickly as possible by following [Mozilla's guidelines for reporting bugs.](https://developer.mozilla.org/en-US/docs/Mozilla/QA/Bug_writing_guidelines#General_Outline_of_a_Bug_Report)

## Patches and pull requests

Your patches are welcome. Here's our suggested workflow:
 
* Fork the project.
* Make your feature addition or bug fix.
* Send us a pull request with a description of your work. Bonus points for topic branches!

## Copyright and attribution

Copyright (c) 2018 University of Nebraska. Released under the [MIT License](https://github.com/datamade/your-repo-here/blob/master/LICENSE).
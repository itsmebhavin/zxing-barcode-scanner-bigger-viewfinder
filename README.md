Viewfinder (crop) area can be increased by changing the "MAX_FRAME_WIDTH" and "MAX_FRAME_HEIGHT" in "CameraManager.java" (lines 44 and 45). CameraManager.java can be found in:

yourproject/plugins/com.phonegap.plugins.barcodescanner/src/android/LibraryProject/src/com/google/zxing/client/android/camera/CameraManager.java

After that you have to re-build the library project:

So assuming you have the Android SDK and tools (ie: ant) then what you need to do is go to the directory:

yourpoject\plugins\com.phonegap.plugins.barcodescanner\src\android\LibraryProject

you'll need to put a local.properties file in this folder, or make one, it only needs one line: sdk.dir=path/to/your/android/sdk

then assuming you have all the correct build tools and api packages (i did not, had to open my sdk manager and install build tools 19.1 and api 17) you would just need to run: ant release

which will build the executable jar, which for me showed up as: yourpoject\plugins\com.phonegap.plugins.barcodescanner\src\android\LibraryProject\bin\classes.jar

so rename it to: com.google.zxing.client.android.captureactivity.jar and put it under: yourpoject\plugins\com.phonegap.plugins.barcodescanner\src\android\

also, to avoid removing/re-adding the platform (to redeploy the plugin) i also copied the file to: yourproject\platforms\android\libs\com.google.zxing.client.android.captureactivity.jar

then just built the project.
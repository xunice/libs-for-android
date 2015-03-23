

# Building the libraries #
  1. Install the latest [Android SDK](http://developer.android.com/sdk/)
  1. Install [Apache Ant](http://ant.apache.org/)
  1. Get the libs-for-android [source](http://code.google.com/p/libs-for-android/source/checkout) code
  1. Create a file called `local.properties` in `libs-for-android/` containing the location of the SDK.  For example:
```
sdk.dir=C:/android-sdk-windows
```
  1. Build the libraries with the command `ant`
  1. The compiled JARs will be placed in the output directory `libs-for-android/bin/`

# Using the libraries #
  1. Copy the JAR files to the `libs/` directory of your Android application
  1. If you are using Eclipse, add the JAR files to your project build path.  If you are using Ant, the libraries will be automatically recognized when they are added to `libs/`.

# Building the demos #
  1. Install the latest [Android SDK](http://developer.android.com/sdk/)
  1. Install [Apache Ant](http://ant.apache.org/)
  1. Get the libs-for-android [source](http://code.google.com/p/libs-for-android/source/checkout) code
  1. Run the command `android update project` to create `local.properties`
  1. Build the demo with the command `ant debug`

**Tip:** You can run the same command for all the demos at once using the Python script `tools/demos.py`.  For example,
```
python demos.py 'android update project -p .'
python demos.py 'ant install'
```

# Using Eclipse #
  * Install the latest [Android SDK](http://developer.android.com/sdk/) and the [ADT Plugin for Eclipse](http://developer.android.com/sdk/eclipse-adt.html)
  * [Configure](http://developer.android.com/sdk/eclipse-adt.html#configuring) the ADT Plugin
  * The libraries are a standard Java project and can be imported with _File -> Import... -> Existing Projects into Workspace._.  The project file is in `libs-for-android/`.
  * The demos are standard Android projects and can be imported with _File -> Import... -> Existing Projects into Workspace_.  You may need to manually perform a clean build to create the output directories.

# Getting Help #
If you can't find the information you're looking for in the documentation, you can post your question to Stack Overflow with the tag [libs-for-android](http://stackoverflow.com/questions/tagged/libs-for-android).
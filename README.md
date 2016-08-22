# MogeanSDK-Android

1. Download the .aar file and place this .aar file in your libs folder. 
2. In your build.gradle file, add the dependency:

    `compile 'org.altbeacon:android-beacon-library:2.6.1'`
    
    `compile 'com.google.android.gms:play-services:8.1.0'`
    
    `compile(name:'mogean-release', ext:'aar')`

3. Import the package:

    `import com.mogeansdk.mogean.*;`


4. Invoke the Mogean Service using the sample code below: 

    `Intent in = new Intent(this, MogeanService.class);`
    
    `in.putExtra("MogeanID", "<Your Mogean Provided MogeanID>");`
    
    `in.putExtra("MogeanConsumerKey", "<Your Mogean Provided Mogean Consumer Key>");`
    
    `in.putExtra("EnableNotifications", false);`
    
    `startService(in);`

5. Done!

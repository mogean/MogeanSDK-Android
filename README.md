# MogaenSDK-Android

1. Download the .aar file and place this .aar file in your libs folder. 
2. In your build.gradle file, add the dependency: 
    compile(name:'MogeanSDK', ext:'aar')
3. Import the package: import com.mogeansdk.mogean.*;
4. Invoke the Mogean Service using the sample code below: 
        Intent in = new Intent(this, MogeanService.class);
        in.putExtra("MogeanID", "<Your Mogean Provided MogeanID>");
        in.putExtra("EnableNotifications", true);
        startService(in);

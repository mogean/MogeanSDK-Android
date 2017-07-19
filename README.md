# MogeanSDK-Android

###Download the .aar file and place this .aar file in your libs folder
###In your build.gradle file, add the dependency
```java
compile 'org.altbeacon:android-beacon-library:2.9.2'
compile 'com.google.android.gms:play-services:7.8.0'
compile(name:'mogean-release', ext:'aar')
```
###Import the package
```java
import com.mogeansdk.mogean.*;
```
###Invoke the Mogean Service using the sample code below
```java
Intent in = new Intent(this, MogeanService.class);
in.putExtra("MogeanID", "<Your Mogean Provided MogeanID>");    
in.putExtra("MogeanConsumerKey", "<Your Mogean Provided Mogean Consumer Key>");    
in.putExtra("EnableNotifications", false);
startService(in);
```
###Done!

# How to get Advertising Identifier

###Below is the code to get this
```
    private class GetAdvertisingIdentifierAsyncTask extends AsyncTask<Void, Void, String> {

    @Override
    protected String doInBackground(Void... voids) {
            AdvertisingIdClient.Info idInfo = null;
            try {
                idInfo = AdvertisingIdClient.getAdvertisingIdInfo(context);
            } catch (GooglePlayServicesNotAvailableException e) {
                e.printStackTrace();
            } catch (GooglePlayServicesRepairableException e) {
                e.printStackTrace();
            } catch (IOException e) {
                e.printStackTrace();
            }
            String advertId = null;
            try{
                advertId = idInfo.getId();
                isAdTrackingEnabled = idInfo.isLimitAdTrackingEnabled();
            }catch (NullPointerException e){
                e.printStackTrace();
            }
            return advertId;
        }

        @Override
        protected void onPostExecute(String result) {
            Log.i(TAG, "AdvertisingIdentifier is : " + result);
            advertisingIdentifier = result;
        }
    }
```
